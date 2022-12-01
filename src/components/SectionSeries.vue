<script>
import { store } from "../store.js";
import "/node_modules/flag-icons/css/flag-icons.min.css";

export default {
  name: 'SectionSeries',
  data() {
    return {
      store,
    };
  },
  methods: {
    getFlag(lang) {
      if (lang === "en") {
        return "gb";
      } else if (lang === "ko") {
        return "kr";
      } else return lang;
    },
    vote(serie) {
      return Math.ceil(serie.vote_average / 2);
    },
  },
}
</script>

<template>
  <ul>
    <li v-for="serie in store.series">
      <div>{{ serie.name }}</div>
      <div v-if="(serie.name != serie.original_name)">{{ serie.original_name }}</div>
      <span :class="`fi fi-${getFlag(serie.original_language)}`"></span>
      <div>
        <i class="fa-solid fa-star" v-for="n in vote(serie)"></i>
        <i class="fa-regular fa-star" v-for="n in (5 - vote(serie))"></i>        
      </div>
      <img :src="`https://image.tmdb.org/t/p/w342${serie.poster_path}`" alt="">
    </li>

  </ul>
</template>

<style>
</style>