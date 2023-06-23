<template>
  <div class="main">
    <h3>
      Main
    </h3>
    <AppSearchBar @buttonClicked="getAll"/>
    <AppListMovie :list-movie="listMovie" :list-Series="listSeries" />
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
      apiUrlMovie: 'https://api.themoviedb.org/3/search/movie',
      apiUrlSeries: 'https://api.themoviedb.org/3/search/tv',
      listMovie: [],
      listSeries: [],
    };
  },
  name: "AppMain",
  components: {
    AppSearchBar,
    AppListMovie,
  },
  methods: {
    getAll(searchedText) {
      this.getMovies(searchedText);
      this.getSeries(searchedText);
    },
    getMovies(film) {
      axios
        .get(this.apiUrlMovie, {
          params: {
            query: film,
            api_key: "aa2c63995be04027118ba87fe065cf4e"
          }
        })
        .then((response) => {
          this.listMovie = response.data.results;
          console.log(this.listMovie);
        })
        .catch(function (error) {
          console.log(error);
        });
    },
    getSeries(singleSeries) {
      axios
        .get(this.apiUrlSeries, {
          params: {
            query: singleSeries,
            api_key: "aa2c63995be04027118ba87fe065cf4e"
          }
        })
        .then((response) => {
          this.listSeries = response.data.results;
          console.log(this.listSeries);
        })
        .catch(function (error) {
          console.log(error);
        });
    },
  },
  created() {
    this.getMovies();
    this.getSeries();
  },
};
</script>

<style lang="scss" scoped>
.main {
  border: 1px solid black;
}
</style>
