<template>
  <div class="main">
    <h3>
      Main
    </h3>
    <AppSearchBar/>
    <AppListMovie/>
  </div>
</template>
<script>
import { store } from '../store.js';
import axios from 'axios';
import AppSearchBar from './AppSearchBar.vue';
import AppListMovie from './AppListMovie.vue';
export default {
  data() {
    return {
      store,
      apiUrl:'https://api.themoviedb.org/3/search/movie?api_key=aa2c63995be04027118ba87fe065cf4e',
      listMovie:[],
    }
  },
  name: "AppMain",
  components:{
    AppSearchBar,
    AppListMovie,
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
}
</script>
<style lang="scss" scoped>
  .main{
    border: 1px solid black;
  }
</style>