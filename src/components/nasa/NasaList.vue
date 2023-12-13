<template>
    <div>
    <div>
        Fecha Inicio: <input v-model="FechaInicio" id="FechaInicio" type="text" name="FechaInicio"  placeholder="YYYY-MM-DD" >
        <br/><br/>
        Fecha Final:<input v-model="FechaFin" id="FechaFin" type="text" name="FechaFin"  placeholder="YYYY-MM-DD" >
        <br/><br/>
        <input type="button" value="Buscar" @click="BuscarImagenes">
    </div>

    

  </div>
<div class="titulo-lista"><h6> APOD </h6></div>

<div class="nasa-list">
    <div class="nasa-grid">
        <div class="nasa-item" v-for="nasa in nasas" :key="nasa.title">
            <NasaItem :nasa="nasa" />
        </div>
    </div>
</div>
</template>

<style>
.dropdown {
display: flex;
justify-content: right;
margin-left: 3%;

}
.titulo-lista {
margin-left: 2%;
}
.nasa-grid {
display: grid;
grid-template-columns: repeat(4, 1fr);
grid-gap: 60px;
}
.nasa-item {
margin-left: 5%;
}

</style>

<script>
import NasaItem from 'components/nasa/NasaItem.vue'
import axios from 'axios'


export default {
name: "NasaList",
components: {
    NasaItem
},

mounted() {
    this.getNasa()

},

methods: {
    getNasa() {

        //var page = this.selectedNumber
        var url = "https://api.nasa.gov/planetary/apod?api_key=K532UCdzQlbtXG3ArfI1ssIa7P1aVxi0ovI1ylqb&start_date=2023-12-01&end_date=2023-12-08"
     
        axios.get(url)
            .then(response => {
                this.nasas = response.data
                console.log(response.data)
            }).catch(error => {
                console.log("Error: " + error)
            })

    },

    BuscarImagenes(){
        var url = "https://api.nasa.gov/planetary/apod?api_key=K532UCdzQlbtXG3ArfI1ssIa7P1aVxi0ovI1ylqb&start_date="+this.FechaInicio+"&end_date="+this.FechaFin
     
        axios.get(url)
            .then(response => {
                this.nasas = response.data
                console.log(response.data)
            }).catch(error => {
                console.log("Error: " + error)
            })
    }

},

data() {
    return {
        nasas: [],
    }
},

}

</script>