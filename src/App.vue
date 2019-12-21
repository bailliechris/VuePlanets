<template>
  <div id="app">
    <Header />   
    <PlanetMan />
  
  </div>
</template>

<script>
import Header from './components/Header'
import PlanetMan from './components/planetsManager'

export default {
  name: 'app',
  components: {
    Header,
    PlanetMan
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
  margin-top: auto;
}
</style>
