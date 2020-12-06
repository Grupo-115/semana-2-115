<template>
    <div>
        <div class="container ">
            <div class=" card-deck mt-5 p-2 ">
                <div class="card text-white bg-dark m-3 text-center " v-for="item in miembros" :key="item.id">
                    <img :src="item.image"  class="card-img-top " alt='imagen de miembros'>
                    <h5 class="card-title m-2">{{item.nombre}}</h5>
                    <p class="card-text m-2">{{item.descripcion}}</p>
                </div>
            </div>
        </div>
        
    </div>
</template>

<script>
import miembrosData from "../assets/miembros.json"
export default {
name: "TeamCard",
data(){
    return{
        miembros: miembrosData.team
    }
},
}
</script>
<style scoped>
.container{
    background-color:gainsboro ;
    border-radius: 10px;
}
/* .con{
    background-color:lemonchiffon;
    display: flex;
    align-content: space-evenly;
    margin: 4%;
} */
</style>