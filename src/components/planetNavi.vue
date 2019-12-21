<template>
    <div>
        <form>
            <input v-on:click="$emit('prev-planet')" type="Button" value="Previous">
            <input v-on:click="$emit('next-planet')" type="Button" value="Next">
        </form>
    </div>
</template>

<script>
export default {
    name: "Navi"
}
</script>

<style scoped>
form {
    display: flex;
}

input[type="button"]{
    background-color:darkslategrey;
    border: 1px;
    color:white;
    padding: 5px 5px;
    text-decoration: none;
    cursor: pointer;
    flex:2;
}  
</style>