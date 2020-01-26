<template>
  <div class="container-input-text">
    <app-inputs></app-inputs>
    <app-text-area></app-text-area>
  </div>
</template>

<script>
import TextArea from './modules/Inputs.vue'
import Inputs from './modules/TextArea.vue'

  export default {
    components: {
      appTextArea: TextArea,
      appInputs: Inputs
    }
  }
</script>

<style lang="scss" scoped>

  .container-input-text {
    display: flex;
    align-items: flex-start;
    margin: 20px;
  }

</style>