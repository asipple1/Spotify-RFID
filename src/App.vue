<template>
  <div id="app">
    <spotify/>
  </div>
</template>

<script>
import spotify from './components/spotify'


export default {
  name: 'App',
  components: {
    spotify
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
