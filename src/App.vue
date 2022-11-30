<script>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import AppFooter from './components/AppFooter.vue'
import { store } from "./store";
import axios from "axios";

export default {
  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    getMovies() {
   
      axios
      .get("https://api.themoviedb.org/3/search/movie", {
        params: {
          api_key: "f7b76ba2478549a1bce670920b20220b",
          query: this.store.searchText,
          language: "it-IT",
        },
      })
      .then((res) => {
       this.store.movies = res.data.results;
      });
    },
  },
  
};
</script>

<template>
  <div class="container">
    <AppHeader  @cliccato="getMovies"/>
    <AppMain />
    <AppFooter />
  </div>
</template>

<style lang="scss">
@import './style/global.scss';
</style>
