<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
     <contenu></contenu>
     <header-top></header-top>

  </div>
</template>

<script>
import Contenu from './components/Contenu.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    'contenu': Contenu,
    'header-top': Header
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
