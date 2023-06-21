<template>
  <nav class="navbar bg-body-tertiary">
  <div class="container-fluid">
    <form class="d-flex" role="search">
      <input class="me-2" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-outline-success" type="button">Search</button>
    </form>
  </div>
</nav>
</template>
<script>
import axios from 'axios';
export default {

  data() {
    return {
      filteredMovie:[],
      searchedText : ''
    }
  },
}
</script>
<style lang="scss" scoped>
    
</style>