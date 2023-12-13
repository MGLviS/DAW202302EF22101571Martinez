<template>
    <div>

      <div class="sticky-header">
        <h5>APOD</h5>
        <div class="nasa-title"><br/>
        <div class="btn-fav">
          <!-- <MovieFav ref="MovieFav" /> -->
          <!-- <div class="agregar">
            <q-btn @click="nasaf" color="red" icon="favorite" label="Mis Favoritos" />
            <br />
          </div> -->
        </div>
    </div>
      </div>
  
      <div class="nasa-page">
        <div class="nasa-list">
          <NasaList />
        </div>
      </div>
    </div>
  </template>
  
  <style>
  .sticky-header {
    position: sticky;
    top: 0;
    background-color: white;
    z-index: 1000;
    display: flex;
    justify-content: space-between;
    padding: 10px;
    display: flex;
  }
  
  .nasa-title {
    text-align: center;
    font-size: 150%;
    margin-top: 2%;
  }
  
  .nasa-page {
    display: flex;
    justify-content: space-between;
  }
  
  .nasa-list {
    width: 99%;
  }
  
  .btn-fav {
    text-align: left;
    margin-left: 0%;
  }
  </style>
  

<script>

import NasaList from 'src/components/nasa/NasaList.vue'
// import MovieFav from 'src/components/nasa/MovieFav.vue'
export default {
    name: "NasaPage",
    components: {
        NasaList,
        //MovieFav
    },

    methods: {
        // nasaf(){
        //     this.$refs.MovieFav.abrirModalnuevoV();
        // }
    }
}
</script>