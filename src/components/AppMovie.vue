<template>
    <section class="d-flex">
        <div class="movie-container mt-3 d-flex">
        <div class="card" style="width: 18rem;">
              <img class="card-img-top" :src="`http://image.tmdb.org/t/p/w500/${imageMovie}`" alt="titleMovie">
        <div class="card-body">
          <h5 class="card-title">{{ titleMovie }}</h5>
          <p class="card-text">{{ titleOriginal }}</p>
          <div v-if="flagsImgList.includes(language + '.svg')">
              <img class="flags-language" :src="getImageLanguage(language)" alt="language">
            </div>
            <div v-else>
              {{ language }}
            </div>
             <p>
              Voto:
              <span class="star" v-for="star in Math.round(rank / 2)">
                <i class="fas fa-star"></i>
              </span>
              <span class="empty-star" v-for="emptyStar in 5 - Math.round(rank / 2)">
                <i class="far fa-star"></i>
              </span>
            </p>
        </div>
      </div>
          </div>
          <div class="tv-container mt-3">
        <div class="card" style="width: 18rem;">
                  <img class="card-img-top" :src="`http://image.tmdb.org/t/p/w500/${imageSeries}`" alt="titleMovie">
        <div class="card-body">
          <h5 class="card-title">{{ titleSeries }}</h5>
          <p class="card-text">{{ titleOriginalSeries }}</p>
          <div v-if="flagsImgList.includes(languageSeries + '.svg')">
              <img class="flags-language" :src="getImageLanguage(languageSeries)" alt="language">
            </div>
            <div v-else>
              {{ language }}
            </div>
             <p>
              Voto:
              <span class="star" v-for="star in Math.ceil(rank / 2)">
                <i class="fas fa-star"></i>
              </span>
              <span class="empty-star" v-for="emptyStar in 5 - Math.ceil(rank / 2)">
                <i class="far fa-star"></i>
              </span>
            </p>
        </div>
      </div>
          </div>
    </section>
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
      imageSeries: String,
    },
    data() {
      return {
        flagsImgList: [
          "de.svg",
          "es.svg",
          "fr.svg",
          "en.svg",
          "it.svg",
          "ja.svg",
          "um.svg",
        ],
      };
    },
    methods: {
      getImageLanguage(img) {
        return new URL(`../assets/${img}.svg`, import.meta.url);
      },
    },
  };
  </script>
  
  <style lang="scss" scoped>
  .flags-language {
    height: 30px;
  }
  </style>
  