<template>
    <nav class="flex border-b font-bold gap-4 p-4">
        <a v-for="(page, index) in pages" v-bind:key="index"
            v-bind:class="[activePage == index ? 'text-green-400' : '', 'cursor-pointer']" v-bind:href="page.link.url"
            :title="`This links to ${page.link.text.toLowerCase()} page`"
            v-on:click.prevent="navbarLink(index)">{{ page.link.text }}</a>
    </nav>
</template>
<script>

export default {
    props: ['pages', 'activePage', 'navbarLink'],
}
</script>