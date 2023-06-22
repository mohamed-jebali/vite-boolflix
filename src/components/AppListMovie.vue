<template>
   <div>
       <AppMovie v-for="itemMovie in listMovie"
       :titleMovie="itemMovie.title"
       :titleOriginal="itemMovie.original_title"
       :language="itemMovie.original_language"
       :rank="itemMovie.vote_average"
       />
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
        listMovie : Array,
    },
}
</script>
<style lang="scss" scoped>

</style>