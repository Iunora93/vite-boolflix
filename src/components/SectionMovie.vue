<script>
import { store } from "../store.js";

export default {
  name: 'SectionMovie',
  data() {
    return {
      store,
    };
  },
}
</script>

<template>
  <ul>
    <li v-for="movie in store.movies">
      <div>{{ movie.title }}</div>
      <div v-if="(movie.title != movie.original_title)">{{ movie.original_title }}</div>
      <div>{{ movie.original_language }}</div>
      <div>{{ movie.vote_average }}</div>
      <img :src="`https://image.tmdb.org/t/p/w342${movie.poster_path
}`" alt="">
    </li>

  </ul>
</template>

<style>
</style>