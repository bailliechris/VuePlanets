<template>
  <div id="app">
    <Header />
    <AddPlanet v-on:add-planet="addPlanet" />
    <Planets v-bind:planets="planets" />
  </div>
</template>

<script>
import Header from './components/Header'
import Planets from './components/Planets'
import AddPlanet from './components/addPlanets'
//import Axios from 'axios'

export default {
  name: 'app',
  components: {
    Header,
    Planets,
    AddPlanet
  },
  data(){
    return{
      planets:[
        {
          id:"0",
          name:"Earth",
          desc:"Mostly Harmless",
          image: "https://www.publicdomainpictures.net/pictures/90000/nahled/planet-earth-1401465698wt7.jpg"
        }
      ]
    }
  },
  methods:{
    addPlanet(newPlanet) {
      this.planets.push(newPlanet);

     // axios.put("https://api.myjson.com/bins/ev42s", this.todos);
    //  .then(res => this.todos = [...this.todos, res.data]);
    }
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
