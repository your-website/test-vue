<template>
  <header class="header">
    <Slide right>
      <a id="home" href="#">
        <span>Home</span>
      </a>
    </Slide>
  </header>
</template>

<script>
import { Slide } from 'vue-burger-menu'
  export default {
    components: {
        Slide
    }
}
</script>

<style lang="scss" scoped>

  .header {
      height: 15vh;
      background-color: $bgc-header;
  }

  .bm-menu {
      height: 100%; /* 100% Full-height */
      width: 0; /* 0 width - change this with JavaScript */
      position: fixed; /* Stay in place */
      z-index: 1000; /* Stay on top */
      top: 0;
      left: 0;
      background-color: rgb(19, 19, 207); /* Black*/
      overflow-x: hidden; /* Disable horizontal scroll */
      padding-top: 60px; /* Place content 60px from the top */
      transition: 0.5s; /*0.5 second transition effect to slide in the sidenav*/
    }

</style>