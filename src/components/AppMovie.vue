<template>
    <div class="movie-container">
        <h3>
            {{ titleMovie }}
        </h3>
        <h4>
            {{ titleOriginal }}
        </h4>
        <div v-if="flagsImgList.includes(language + '.svg')">
            <img :src="getImageLanguage(language)" alt="country flag">
        </div>
            <div v-else>
                {{ language }}
        </div>
        <p>
            {{ rank }}
        </p>
    </div>
    <div class="tv-container">
        <h3>
            {{ titleSeries }}
        </h3>
        <h4>
            {{ titleOriginalSeries }}
        </h4>
        <div v-if="flagsImgList.includes(languageSeries + '.svg')">
            <img :src="getImageLanguage(languageSeries)" alt="country flag">
        </div>
            <div v-else>
                {{ languageSeries }}
        </div>
        <p>
            {{ rankSeries }}
        </p>
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
        // ------------------
        titleSeries: String,
        titleOriginalSeries: String,
        languageSeries: String,
        rankSeries: Number,
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
            ]
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
img{
    height: 30px;
}
</style>

