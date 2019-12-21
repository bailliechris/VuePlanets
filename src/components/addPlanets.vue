<template>
    <div>
        <form @submit="addPlanet">
            <input type="text" name="name" v-model="name" placeholder="Add a planet name...">
            <input type="text" name="desc" v-model="desc" placeholder="Add a planet description...">
            <input type="text" name="image" v-model="image" placeholder="Add a planet image URL...">
            <input type="submit" value="Add" class="btn">
        </form>
    </div>
</template>

<script>
import uuid from "uuid";

export default {
    name:"AddPlanet",
    data() {
        return {
            name:"",
            desc:"",
            image:""
        }
    },
    methods: {
        addPlanet(e) {
            e.preventDefault();
            const newPlanet = {
                id: uuid.v4(),
                name: this.name,
                desc: this.desc,
                image: this.image
            }
            //Send to parent
            this.$emit('add-planet', newPlanet);

            this.name = "";
            this.desc = "";
            this.image = "";
        }
    }
}
</script>

<style scoped>
form {
    display: flex;
}

input[type="text"]{
    flex:10;
    padding:5px;
}

input[type="submit"]{
    background-color:rgb(243, 161, 9);
    border: none;
    color:white;
    padding: 5px 5px;
    text-decoration: none;
    cursor: pointer;
    flex:2;
}  
</style>