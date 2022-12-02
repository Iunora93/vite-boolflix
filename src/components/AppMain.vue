<script>
import { store } from "../store.js";

import AppCard from './AppCard.vue'

export default {
  name: 'AppMain',
  components:{
  
    AppCard,
  },
  data() {
    return {
      store,
    };
  },
}
</script>

<template>
  <main>
    <h2 v-if="(store.movies.length > 0)">Movie</h2>
    <AppCard :details="movie" v-for="movie in store.movies" />
    <h2 v-if="(store.series.length > 0)">Serie</h2>
    <AppCard :details="serie" v-for="serie in store.series" />
  </main>
</template>

<style lang="scss" scoped>
main{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  h2{
    color: white;
    text-align: center;
    width: 100%;
    margin-top: 20px;
    border: 1px solid white;
  }
}
</style>