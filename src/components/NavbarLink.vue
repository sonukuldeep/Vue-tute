<template>
    <a class="" :class="activeClasses" v-bind:href="page.link.url"
        :title="`This links to ${page.link.text.toLowerCase()} page`">{{
            page.link.text }}</a>
</template>

<script>
export default {
    props: ['page', 'isActive'],
    computed: {
        activeClasses() {
            return {
                emphasize: this.isActive
            }
        }
    }
}
</script>

<style scoped>
.emphasize {
    color: teal;
}
</style>