<template>
   <div>
       <AppMovie v-for="item in listMovie"
       :titleMovie="item.title"
       :titleOriginal="item.original_title"
       :language="item.original_language"
       :rank="item.vote_average"
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
        listMovie : Array
    },
}
</script>
<style lang="scss" scoped>

</style>