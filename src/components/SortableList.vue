<script>
    import { Sortable } from '@shopify/draggable'
    function move(items, old_index, new_index) {
        const item_removed_array = [
            ...items.slice(0, old_index),
            ...items.slice(old_index + 1, items.length)
        ]

        return [
            ...item_removed_array.slice(0, new_index),
            items[old_index],
            ...item_removed_array.slice(new_index, item_removed_array.length)
        ]
    }
    export default {
        props: {
                value: {
                    required: true
                },
                itemClass: {
                    default: 'sortable-item'
                },
                handleClass: {
                    default: 'sortable-handle'
                }
        },
        provide() {
            return {
                itemClass: this.itemClass,
                handleClass: this.handleClass,
            }
        },
        render() {
            return this.$scopedSlots.default({
                items: this.value
            })
        },
        mounted() {
            new Sortable(this.$el, {
                draggable: `.${this.itemClass}`,
                handle: `.${this.handleClass}`,
                mirror: {
                    constrainDimensions: true,
                },
            }).on('sortable:stop', ({oldIndex, newIndex}) => {
                this.$emit('input', move(this.value, oldIndex, newIndex))
            })
        }
    }

</script>

<style>
    .sortable-handle:hover{
        cursor: grab;
        cursor: -moz-grab;
        cursor: -webkit-grab;
    }
    .sortable-handle:active {
        cursor: grabbing;
        cursor: -moz-grabbing;
        cursor: -webkit-grabbing;
    }
</style>
