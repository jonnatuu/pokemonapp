<template>
  <div id="app">
    <h1> Pokemon APP</h1>
    <Pokemons />
  </div>
</template>

<script>
import Pokemons from './components/TellJoke.vue'

export default {
  name: 'App',
  components: {
    Pokemons
  }
}
</script>

<style src="../css/style.css">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
