
<template>
    <div class="container-inputs">
      <label 
        class="container-inputs__label" 
        for="font-size"
      >Введите размер шрифта</label>

      <input
        name="font-size"
        v-on:input="changeSizeText"
        v-model="fontsize"
        type="number"
      >

      <label 
        class="container-inputs__label" 
        for="font-family"
      >Введите шрифт</label>

      <input
        name="font-family"
        v-on:input="changeFontFamily"
        v-model="fontfamily"
        type="string"
      >

      <label 
        class="container-inputs__label" 
        for="color-text"
      >Выберите цвет</label>
      
      <div class="container-color-picker">
        <input
          name="color-text"
          class="container-inputs__input-color"
          v-on:input="changeColor"
          v-model="color"
          type="color"
          value=""
        >
      </div>
    </div>
</template>

<script>
import { eventEmitter } from '../../../main.js'
  export default {
    data() {
      return {
        color: '#4e4ac1',
        fontsize: "",
        fontfamily: ""
      }
    },
    methods: {
      changeColor: function() {
        eventEmitter.$emit('changeColor', this.color);
      },
      changeSizeText: function() {
        eventEmitter.$emit('changeSizeText', this.fontsize);
      },
      changeFontFamily: function() {
        eventEmitter.$emit('changeFontFamily', this.fontfamily);
      },
    }
  }
</script>

<style lang="scss" scoped>
  .container-inputs {
    display: flex;
    flex-direction: column;
    margin-left: 40px;
  }

  input {
    border: 1px solid black;
    outline: none;
    margin-bottom: 10px;
    max-width: 70px;
    box-sizing: border-box;
    
    &:focus {
      border: 1px solid rgb(223, 113, 10);
    }
  }

  .container-color-picker {
    width: 32px;
    height: 32px;
    overflow: hidden;
    border-radius: 50%;
    margin: 0;
    display: inline-block;
    border: 1px solid #ccc;
  }

  .container-inputs__input-color {
    width: 32px;
    padding: 0;
    border: none;
    height: 32px;
    outline: none;
    box-shadow: 0 0 0 0;
    -moz-kit-appearance: none;
  }

  .container-inputs__input-color::-webkit-color-swatch-wrapper {
    padding: 0;
  }

  .container-inputs__input-color::-webkit-color-swatch {
    border: none;
  }

  .container-inputs__label {
    margin-bottom: 5px;
  }
</style>