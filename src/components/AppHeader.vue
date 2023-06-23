<template>
<nav class="navbar bg-body">
  <div class="container-fluid">
    <img src="../assets/boolflix_logo.png" alt="">
    <ul class="d-flex">
      <li>Home</li>
      <li>Serie Tv</li>
      <li>Film</li>
      <li>Originali</li>
      <li>Aggiunti di recente</li>
      <li>La mia Lista</li>
    </ul>
    <div>
      
    </div>
  </div>
</nav>
  </template>
  <script>
  export default {
    name:"AppHeader",
    data() {
      return {
      }
    },
  }
  </script>
  <style lang="scss" scoped>
  nav{
    background-color: #1b1b1b !important;
  }
    img{
      height: 50px;
    }
    ul{
      list-style-type: none;
      li{
        margin-right: 1rem;
      }
    }
  </style>