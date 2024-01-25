<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <vr-input label="Enter input.." type="date" v-model="inputValue"/>
  <vr-button type="button">Save</vr-button>
  
</template>

<script setup>
import {ref} from 'vue'
import VrInput from './components/Input/VrInput.vue'
import VrButton from './components/Button/VrButton.vue';

const inputValue = ref('')

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
