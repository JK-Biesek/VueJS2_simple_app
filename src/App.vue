<template>
  <div id="app">
    <img src="./assets/logo.png">
    <skills msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import skills from './components/skills.vue'

export default {
  name: 'app',
  components: {
    skills
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
