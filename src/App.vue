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
@import url('https://fonts.googleapis.com/css?family=Open+Sans');
body {
  background-color: #d68f27;
  color: #fff;
  font-family: 'Open Sans', sans-serif;
}
</style>
