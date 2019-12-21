<template>
  <div id="app">
    <Header />
    <AddPlanet v-on:add-planet="addPlanet" />
    <Planets v-bind:planets="planets" v-on:del-planet="deletePlanet"/>
  </div>
</template>

<script>
import Header from './components/Header'
import Planets from './components/Planets'
import AddPlanet from './components/addPlanets'
import Axios from 'axios'

export default {
  name: 'app',
  components: {
    Header,
    Planets,
    AddPlanet
  },
  data(){
    return{
      index:0,
      planets:[

      ]
    }
  },
  methods:{
    deletePlanet(id) {
      this.planets = this.planets.filter(element => element.id !== id)
      Axios.put("https://api.myjson.com/bins/hmp6o", this.planets)
    },
    addPlanet(newPlanet) {
      this.planets.push(newPlanet);

      Axios.put("https://api.myjson.com/bins/hmp6o", this.planets)
      .then(res => this.planets = res.data);
    }
  },
  created() {
      this.index = 0;
      Axios.get("https://api.myjson.com/bins/hmp6o")
      .then(res => this.planets = res.data);
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
