<template>
  <main class="main">
      <app-input-text></app-input-text>
  </main>
</template>

<script>
import InputText from '../InputText/InputText.vue'

  export default {
      components: {
      appInputText: InputText
    }
  }
</script>

<style lang="scss" scoped>

  .main {
      height: 60vh;
      background-color: $bgc-main;
      display: flex;
      justify-content: space-around;
      align-items: flex-start;

      padding-top: 10vh;

  }

</style>