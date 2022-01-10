<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <normal-mode></normal-mode>
  </div>
</template>

<script>
import Demo from './components/Demo.vue';

export default {
  name: 'App',
  components: {
    'normal-mode': Demo,
  },
};
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
