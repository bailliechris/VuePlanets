<template>
    <div class = "planet-item">
        <h1>{{planet.name}}</h1>
        <p>{{planet.desc}}</p>
        <img v-bind:src="planet.image" width=300>
        
    </div>
</template>

<script>
export default {
    name: "Planet",
    props: ["planet"]

}
</script>

<style scoped>
.planet-item{
    background:cornsilk;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
}

.del {
    background: red;
    color:white;
    border:none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
}

h1{
    color:darkslategray;
    text-align: center;
    font-size: 3rem;
    margin: auto;
}

p{
    color: darkslategray;
    font-size: 2rem;
    text-align:center;
    margin:auto;
    font-size: 1rem;
    padding:10px;
}
</style>