<template>
    <nav class="flex border-b font-bold gap-4 p-4">
        <div v-for="(page, index) in pages">
            <navbar-link :page="page" :isActive="activePage === index" v-on:click.prevent="triggerNavbarLink(index)"></navbar-link>
        </div>
    </nav>
</template>
<script>
import NavbarLink from './NavbarLink.vue';

export default {
    components: {
        NavbarLink,
    },
    props: ['pages', 'activePage','triggerNavbarLink'],
}
</script>