<template>
    <div class="movie-container">
        <h3>
            {{ titleMovie }}
        </h3>
        <h4>
            {{ titleOriginal }}
        </h4>
        <div v-if="flagsImgList.includes(language + '.svg')">
            <img class="flags-language" :src="getImageLanguage(language)" alt="country flag">
        </div>
            <div v-else>
                {{ language }}
        </div>
        <p>
            {{ rank }}
        </p>
        <div class="image-movie-wrapper">
            <img  :src="`http://image.tmdb.org/t/p/w500/${imageMovie}`" alt="`${titleMovie}`">
        </div>
    </div>
    <div class="tv-container">
        <h3>
            {{ titleSeries }}
        </h3>
        <h4>
            {{ titleOriginalSeries }}
        </h4>
        <div v-if="flagsImgList.includes(languageSeries + '.svg')">
            <img class="flags-language" :src="getImageLanguage(languageSeries)" alt="country flag">
        </div>
            <div v-else>
                {{ languageSeries }}
        </div>
        <p>
            {{ rankSeries }}
        </p>
        <div class="image-series-wrapper">
            <img :src="`http://image.tmdb.org/t/p/w500/${imageSeries}`" alt="`${titleSeries}`">
        </div>
    </div>
</template>
<script>
export default {
    name: 'AppMovie',
    props: {
        titleMovie: String,
        titleOriginal: String,
        language: String,
        rank: Number,
        imageMovie: String,
        // ------------------
        titleSeries: String,
        titleOriginalSeries: String,
        languageSeries: String,
        rankSeries: Number,
        imageSeries: String
    },
    data() {
        return {
            flagsImgList:[
                "de.svg",
                "es.svg",
                "fr.svg",
                "en.svg",
                "it.svg",
                "ja.svg",
                "um.svg",
            ],
        }
    },
    methods: {
        getImageLanguage(img){
             return new URL('../assets/'+img+'.svg', import.meta.url);
    },
    },
}
</script>
<style lang="scss" scoped>
.flags-language{
    height: 30px;
}
</style>

