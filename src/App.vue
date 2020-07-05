<template>
  <div id="app">
    <Zoom />
  </div>
</template>

<script>
import Zoom from './components/Zoom.vue'

export default {
  name: 'App',
  components: {
    Zoom
  }
}
</script>

<style>
html, body {
  margin: 0px;
  padding: 0px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #2c3e50;
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
