<template>
  <navbar :pages="pages" :active-page="activePage" :trigger-navbar-link="index => activePage = index"></navbar>

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
  created() {
    this.getPages()
  },
  data() {
    return {
      activePage: 0,
      pages: [],
    }
  },
  methods: {
    async getPages() {
      const res = await fetch('pages.json')
      const data = await res.json()
      this.pages = data
    }
  }
}
</script>