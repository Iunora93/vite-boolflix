<script>
import { store } from "../store.js";
import "/node_modules/flag-icons/css/flag-icons.min.css";

export default {
  name: 'SectionMovie',
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
    vote(movie) {
      return Math.ceil(movie.vote_average / 2);
    },
  },  
};
</script>

<template>
  <ul>
    <li v-for="movie in store.movies">
      <div>{{ movie.title }}</div>
      <div v-if="(movie.title != movie.original_title)">{{ movie.original_title }}</div>
      <span :class="`fi fi-${getFlag(movie.original_language)}`"></span>
      <i class="fa-solid fa-star"></i>
      <i class="fa-regular fa-star"></i>
      <div>{{ vote(movie) }}</div>   
      <img :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" alt="">      
    </li>

  </ul>
</template>

<style>
</style>