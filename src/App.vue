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
    saluta(data) {
      console.log(data);
    },
  },
  created() {
   
    axios
      .get("https://api.themoviedb.org/3/search/movie", {
        params: {
          api_key: "e99307154c6dfb0b4750f6603256716d",
          query: "ritorno",
          language: "it-IT",
        },
      })
      .then((res) => {
        this.store.movies = res.data.results;
      });
  },
}
</script>

<template>
  <div class="container">
    <AppHeader  @cliccato="saluta"/>
    <AppMain />
    <AppFooter />
  </div>
</template>

<style lang="scss">
@import './style/global.scss';
</style>
