<template>
  <div id="app">
    <index></index>
  </div>
</template>

<script>
import Index from './pages/Index.vue'

export default {
  name: 'App',
  components: {
    //HomePage,
    Index
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 0px;
  padding: 0px;
}
</style>
