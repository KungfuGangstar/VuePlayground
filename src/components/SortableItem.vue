<script>

    export default {
        props: [],
        render(){
            return this.$slots.default[0];
        },
        inject: ['itemClass'],
        mounted() {
            this.$el.classList.add(this.itemClass)
        }
    }

</script>
