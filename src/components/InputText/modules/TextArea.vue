
<template>
  <div class="container-text-area">
    <label class="container-text-area__label" for="text">Введите текст</label>
    <textarea
      class="container-text-area__text-area"
      ref="textarea"
      name="text"
      v-bind:cols="cols"
      v-bind:rows="rows"
      v-on:input="changeString"
    ></textarea>
  </div>
</template>

<script>
import { eventEmitter } from '../../../main.js'
  export default {
    data() {
      return {
        rows: 1,
        cols: 18,
        stringLength: 0
      }
    },
    methods: {
      changeString: function(event) {
        let valueLength = Math.ceil(this.stringLength * this.rows);

        if (event.target.value.length < (valueLength - this.stringLength)) {
          this.rows -= 1;
        } else if (event.target.scrollHeight !== event.target.clientHeight) {
          this.stringLength = (event.target.value.length / this.rows) - 1;
          this.rows += 1;
        }
        
        if (event.target.value.length === 0) {
          this.rows = 1;
        }

        if (this.rows > 10) {
          this.rows = 10;
        }
      }
    },
    created() {
      eventEmitter.$on('changeSizeText', (fontsize) => {
        this.$refs.textarea.style.fontSize = fontsize + 'px';
      }),
      eventEmitter.$on('changeFontFamily', (fontfamily) => {
        this.$refs.textarea.style.fontFamily = fontfamily;
      }),
      eventEmitter.$on('changeColor', (color) => {
        this.$refs.textarea.style.color = color;
      })
    }
  }
</script>

<style lang="scss" scoped>

  .container-text-area {
    display: flex;
    flex-direction: column;
  }

  .container-text-area__label {
    margin-bottom: 5px;
  }

  .container-text-area__text-area {
    box-sizing: border-box;
    border: 1px solid black;
    outline: none;
    resize: none;
    &:focus {
      border: 1px solid rgb(223, 113, 10);
    }
  }
</style>