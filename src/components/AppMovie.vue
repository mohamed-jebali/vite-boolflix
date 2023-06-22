<template>
    <div>
        <h3>
            {{ titleMovie }}
        </h3>
        <h4>
            {{ titleOriginal }}
        </h4>
        <div v-if="flagsImgList.includes(language)">
            <img :src="getImageLanguage(language)" alt="country flag">
        </div>
            <div v-else>
                {{ language }}
            </div>
        <p>
            {{ rank.toFixed(1) }}
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

