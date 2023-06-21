<template>
  <nav class="navbar bg-body-tertiary">
  <div class="container-fluid">
    <form class="d-flex" role="search">
      <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-outline-success" type="submit">Search</button>
    </form>
  </div>
</nav>
</template>
<script>
import axios from 'axios';
export default {

  data() {
    return {
      apiUrl:'https://api.themoviedb.org/3/search/movie?api_key=aa2c63995be04027118ba87fe065cf4e',
      filteredMovie:[],
    }
  },
  methods: {
        getMovies(filter){
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
        this.getMovies();
    }
}
</script>
<style lang="scss" scoped>
    
</style>