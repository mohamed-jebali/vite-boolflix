<template>
    <div>
        <h3>
            {{ titleMovie }}
        </h3>
        <h4>
            {{ titleOriginal }}
        </h4>
        <p v-if="language === 'en' ? 'addFlags()' : ''">
            {{ language }}
        </p>
        <p>
            {{ rank.toFixed(1) }}
        </p>
    </div>
</template>
<script>

export default {
    name: 'AppMovie',
    props:{
        titleMovie : String,
        titleOriginal : String,
        language : String,
        rank : Number,
    },
    methods: {
        addFlags(){
            if(language === "en" ){
                language = `<img src="../../public/flags/gb.svg" alt="gb">`
            }
        }
    },
}
</script>
<style lang="scss" scoped>

</style>
