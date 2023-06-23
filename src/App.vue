<script>
import AppMain from './components/AppMain.vue'
import AppHeader from './components/AppHeader.vue'
import './styles/general.scss'

export default{
  data() {
    return {
    }
  },
  name:"App",
  components:{
    AppHeader,
    AppMain,
  },

}

</script>

<template>
<AppHeader/>
<AppMain/>
</template>

<style lang="scss">
@import "./bootstrap/scss/bootstrap";
body{
  background-color: #1b1b1b;
  color: white;
}
</style>
