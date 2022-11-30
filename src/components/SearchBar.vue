<script>
import { store } from "../store.js";

export default {
  name: 'SearchBar',
  data() {
    return {
      store,
    };
  },
}
</script>

<template>
  <input v-model="store.text" type="text" placeholder="Scrivi un film o una serie tv">
  <button type="submit" @click="$emit('cliccato')">Search</button>
  <ul>
    <li v-for="movie in store.movies">{{movie.title}}</li>
  </ul>
</template>

<style>
</style>