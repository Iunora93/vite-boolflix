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
  <header>
    <img src="../assets/BOOLFLIX LOGO.png" alt="">
    <form @submit.prevent="$emit('search')" action="">
      <input v-model="store.searchText" type="text" placeholder="Scrivi un film o una serie tv">
      <button type="submit">Search</button>
    </form>
  </header>
</template>

<style lang="scss" scoped>
header{
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
