<template>
    <q-card class="nasa-card">
        <q-card-section>
            
            <q-img 
                :src="nasa.url"
            >
            </q-img>
        </q-card-section>
        <q-card-section>      
            <div class="text-h6 font-weight-bold">{{ nasa.title }}</div>
            <div >Autor: {{ nasa.copyright }}</div>
            <div >Fecha: {{ nasa.date }}</div>
            <!-- <q-icon name="stars" size="1.8em" color="warning"/> -->
            <!-- {{movie.vote_average}}/10 -->
            <!-- <q-btn
                :disable="favoriteButtonDisabled"
                fab
                icon="favorite"
                color="red"
                size="4em"
                class="absolute"
                style="top: 32px; right: 12px; transform: translateY(-50%);"
                @click="AddFavBtn"
                
            /> -->
            <div class="text-subtitle2">
                <br/>
                
            </div>
      
            <q-expansion-item
                expand-separator
                icon="description"
                label="Ver Mas"
            >
                <q-card>
                <q-card-section>
                {{ nasa.explanation }}
                </q-card-section>
                </q-card>
                </q-expansion-item>
        </q-card-section>
    </q-card>
</template>


<style>
.nasa-card {
    width: 300px;
}

.nasa-card q-card-section {
    height: 100px;
    overflow: hidden;
    
}
</style>


<script>
import { ref } from 'vue'
import axios from 'axios'


export default {
    name: "NasaItem",
    props: {
        nasa: {
            type: Object,
            required: true
        }
    },

    data() {
        return {
            // favoriteButtonDisabled: false
        }
    },

    mounted(){
        // this.VerifyFav()
    },

    methods: {
        // async AddFavBtn() {
        //     console.log("Añadiendo nuevo");
        //     try {
        //         var url = "https://api.themoviedb.org/3/account/20722641/favorite";
        //         var token = "eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiI4YWJlMTE3NWVjNzVkNDY3NDMxNjM4ZjRkYjhhZDFhYiIsInN1YiI6IjY1NWEyODY1NTM4NjZlMDBmZjA5NTkwMSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.uSfAXqK_k6B-LtXJjSFXego87_udgBySiAZV7HdcMno";
        //         var header = {
        //             headers: {
        //                 Authorization: 'Bearer ' + token
        //             }
        //         };

        //         var data = {
        //             media_type: "movie",
        //             media_id: this.movie.id,
        //             favorite: true
        //         };

        //         await axios.post(url, data, header);

        //         this.$q.notify({
        //             message: "Se añadió " + this.movie.title + " correctamente",
        //             color: 'green',
        //             position: 'top',
        //             timeout: 10000
        //         });

        //         this.VerifyFav();
        //         //MovieList();
        //     } catch (error) {
        //         console.error('Error al actualizar:', error);
        //         this.$q.notify({
        //             message: "Ha ocurrido un problema",
        //             color: 'red',
        //             position: 'top',
        //             timeout: 10000
        //         });
        //     }
        // },

        // async VerifyFav() {
        //     try {
        //         var url = "https://api.themoviedb.org/3/account/20722641/favorite/movies?language=en-US&page=1&sort_by=created_at.asc";
        //         var token = "eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiI4YWJlMTE3NWVjNzVkNDY3NDMxNjM4ZjRkYjhhZDFhYiIsInN1YiI6IjY1NWEyODY1NTM4NjZlMDBmZjA5NTkwMSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.uSfAXqK_k6B-LtXJjSFXego87_udgBySiAZV7HdcMno";
        //         var header = {
        //         headers: {
        //             Authorization: 'Bearer ' + token
        //         }
        //         };

        //         const response = await axios.get(url, header);
        //         const movieFavList = response.data.results;

        //         const isFavorite = movieFavList.some(favMovie => favMovie.id === this.movie.id);

        //         this.favoriteButtonDisabled = isFavorite;
        //     } catch (error) {
        //         console.log("Error: " + error);
        //     }
        // }

    }
}
</script>