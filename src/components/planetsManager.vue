<template>
    <div>
        <Navi v-on:prev-planet="prevPlanet" v-on:next-planet="nextPlanet"/>
        <div>
            <Planet v-bind:planet="planets[index]" v-on:del-planet="deletePlanet" />
        </div>
        <AddPlanet v-on:add-planet="addPlanet" />
    </div>
</template>

<script>
import Planet from "./aPlanet.vue"
import Navi from './planetNavi'
import AddPlanet from "./addPlanets"
import Axios from "axios"
export default {
  name: 'PlanetMan',
  components: {
    Planet,
    AddPlanet,
    Navi
  },
  data(){
    return{
      index:0,
      planets:[{
          "id":"0",
          "name":"Loading",
          "desc":"Getting There...",
          "image":"./assets/logo.png"}
      ]
    }
  },
  methods:{
    nextPlanet(){
      this.index = this.index + 1;
      if (this.index > (this.planets.length -1)){
        this.index = 0;
      }
    },
    prevPlanet(){
      if (this.index < 1){
        this.index = this.planets.length - 1;
      } else {
        this.index = this.index - 1;
      }
    },
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
      Axios.get("https://api.myjson.com/bins/hmp6o")
      .then(res => this.planets = res.data);
  }
}
</script>

<style scoped>

</style>