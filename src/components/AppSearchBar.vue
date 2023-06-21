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
      apiUrl:'',
      filteredMovie:[],
      searchedText : ''
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