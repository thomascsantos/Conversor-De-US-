<template>
  <div id="app">
    <ConversorMoeda moeda-a="USD" moeda-b="BRL" />
  </div>
</template>

<script>
import ConversorMoeda from './components/ConversorMoeda.vue';
export default {
  name: 'App',
  components: {
    ConversorMoeda
  }
}
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
body {
    background-image: linear-gradient(45deg, rgb(197, 195, 195), rgb(172, 165, 165));
}
input {
    padding: 20px;
    border-radius: 10px;
    background-color: rgb(204, 211, 212);
    border: none;
    margin-left: 10px;
}
</style>
