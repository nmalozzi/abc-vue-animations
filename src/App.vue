<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <WaterPressure msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import WaterPressure from './layouts/WaterPressure.vue'

export default {
  name: 'App',
  components: {
    WaterPressure
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
