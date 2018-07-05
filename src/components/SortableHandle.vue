<script>

    export default {
        props: [],
        render(){
            return this.$slots.default[0];
        },
        inject: ['handleClass'],
        mounted() {
            this.$el.classList.add(this.handleClass)
        }
    }

</script>

