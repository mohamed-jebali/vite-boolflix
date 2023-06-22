<template>
    <div>
        <h3>
            {{ titleMovie }}
        </h3>
        <h4>
            {{ titleOriginal }}
        </h4>
        <div v-if="flagsImgList.includes(language + '.svg')">
                <img :src="getImageLanguage(language + '.svg')" alt="country flag">
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
                "gb.svg",
                "it.svg",
                "jp.svg",
                "um.svg"
            ]
        }
    },
    methods: {
        getImageLanguage: function (img) {
            return new URL(`../assets/${img}`, import.meta.url).href;
        },  
    },
}
</script>
<style lang="scss" scoped>
img{
    height: 30px;
}
</style>

