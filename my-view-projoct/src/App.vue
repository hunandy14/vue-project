<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <ModernButton>111</ModernButton>
    <ModernButton>222</ModernButton>
    <ModernButton
      backgroundColor="#282c34"
      hoverColor="#79808d"
      activeColor="#21252b"
      afterActiveColor="#cccccc"
      borderWidth="1px"
    >333</ModernButton>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ModernButton from './components/ModernButton.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    ModernButton
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
</style>
