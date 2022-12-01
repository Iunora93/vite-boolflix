<script>
import { store } from "../store.js";


export default {
  name: 'AppHeader',
  data() {
    return {
      store,
    };
  },
}
</script>

<template>
  <form @submit.prevent="$emit('search')" action="">
    <input v-model="store.searchText" type="text" placeholder="Scrivi un film o una serie tv">
    <button type="submit">Search</button>
  </form>
</template>

<style>
</style>
