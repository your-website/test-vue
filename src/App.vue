<template>
  <div>
    <app-header></app-header>
    <app-main></app-main>
    <app-footer></app-footer>
  </div>
</template>

<script>
import Header from './components/Header/Header.vue'
import Footer from './components/Footer/Footer.vue'
import Main from './components/Main/Main.vue'

  export default {
    components: {
      appHeader: Header,
      appFooter: Footer,
      appMain: Main
    }
  }
</script>

<style>
  body {
    margin: 0;
    padding: 0;
  }
</style>