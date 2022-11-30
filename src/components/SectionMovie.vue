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
      <div>{{ movie.original_title }}</div>
      <div>{{ movie.original_language }}</div>
      <div>{{ movie.popularity }}</div>
    </li>

  </ul>
</template>

<style>
</style>