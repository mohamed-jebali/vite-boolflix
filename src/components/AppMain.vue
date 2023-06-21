<template>
  <div>
    <h3>
      Main
    </h3>
  </div>
</template>
<script>
import { store } from '../store.js';
import axios from 'axios';
export default {
  data() {
    return {
      store,
      apiUrl:'https://api.themoviedb.org/3/search/movie?api_key=aa2c63995be04027118ba87fe065cf4e',
      listMovie:[],
    }
  },
    methods: {
        filteredMovie(filter){
            axios.get(this.apiUrl, {
                params: {
                    movie: filter
                }
            })
            .then( (response) => {
            this.listMovie = response.data.data;
            })
            .catch(function (error) {
            console.log(error);
            })
        }    
    },
    created(){
        this.filteredMovie();
    }
}
</script>
<style lang="scss" scoped>
  
</style>