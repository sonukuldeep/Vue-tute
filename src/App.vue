<template>
  <navbar :pages="pages" :active-page="activePage" :navbar-link="index => activePage = index"></navbar>

  <page-viewer v-bind:page-title="pages[activePage].content"
    v-bind:page-content="pages[activePage].content"></page-viewer>
</template>


<script>
import PageViewer from './components/PageViewer.vue';
import Navbar from './components/Navbar.vue';
export default {
  components: {
    Navbar, PageViewer
  },
  data() { // this is state
    return {
      activePage: 0,
      pages: [
        {
          link: { text: 'Home', url: 'index.html' },
          pageTitle: 'Hello from home page',
          content: 'Hello to vue from home page',
        },
        {
          link: { text: 'About', url: 'about.html' },
          pageTitle: 'Hello from about page',
          content: 'Hello to vue from about page',
        },
        {
          link: { text: 'Content', url: 'content.html' },
          pageTitle: 'Hello from content page',
          content: 'Hello to vue from content page',
        },
      ],
    }
  },
}
</script>