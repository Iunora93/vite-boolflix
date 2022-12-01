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
    
    <AppCard :details="movie" v-for="movie in store.movies" />
    
    <AppCard :details="serie" v-for="serie in store.series" />
  </main>
</template>

<style lang="scss" scoped>
main{
  display: flex;
  flex-wrap: wrap;
}
</style>