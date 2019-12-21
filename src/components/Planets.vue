<template>
    <div>
       <div v-bind:key="planet.id" v-for="planet in planets">
           <Planet v-bind:planet="planet" />

        </div>
    </div>
</template>

<script>
import Planet from "./aPlanet.vue"
export default {
    name:"Planets",
    components: {
        Planet
    },
    props: ["planets"]
}
</script>

<style scoped>

</style>