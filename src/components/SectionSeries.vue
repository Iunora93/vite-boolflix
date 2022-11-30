<script>
import { store } from "../store.js";

export default {
  name: 'SectionSeries',
  data() {
    return {
      store,
    };
  },
}
</script>

<template>
  <ul>
    <li v-for="serie in store.series">
      <div>{{ serie.name }}</div>
      <div v-if="(serie.name != serie.original_name)">{{ serie.original_name }}</div>
      <div>{{ serie.original_language }}</div>
      <div>{{ serie.vote_average }}</div>
      <img :src="`https://image.tmdb.org/t/p/w342${serie.poster_path
}`" alt="">
    </li>

  </ul>
</template>

<style>
</style>