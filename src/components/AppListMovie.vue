<template>
   <div>
    <h3>
        List Movie
    </h3>
       <AppMovie/>
    </div>
</template>
<script>
import AppMovie from './AppMovie.vue';
export default {
    data() {
    return {
    }
},
    components:{
             AppMovie,
    },    
    name: 'AppListMovie',
    props : {
        listMovie : Array
    },
}
</script>
<style lang="scss" scoped>

</style>