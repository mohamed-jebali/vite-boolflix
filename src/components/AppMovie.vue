<template>
    <div>
        <h3>
            {{ titleMovie }}
        </h3>
        <h4>
            {{ titleOriginal }}
        </h4>
        <p>
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
    }
}
</script>
<style lang="scss" scoped>

</style>
