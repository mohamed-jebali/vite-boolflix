<template>
   <div>
       <AppMovie v-for="itemMovie in listMovie"
       :titleMovie="itemMovie.title"
       :titleOriginal="itemMovie.original_title"
       :language="itemMovie.original_language"
       :rank="itemMovie.vote_average"
       :imageMovie="itemMovie.backdrop_path"
       />
       <AppMovie v-for="itemSeries in listSeries"
       :titleSeries="itemSeries.name"
       :titleOriginalSeries="itemSeries.original_name"
       :languageSeries="itemSeries.original_language"
       :rankSeries="itemSeries.vote_average"
       :imageSeries="itemSeries.backdrop_path"
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
        listSeries : Array,
    },
}
</script>
<style lang="scss" scoped>

</style>