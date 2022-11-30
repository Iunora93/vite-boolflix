<script>
import { store } from "../store.js";
import SearchBar from '../components/SearchBar.vue'

export default {
  name: 'AppHeader',
  components:{
    SearchBar,
  },
  data() {
    return {
      store,
    };
  },
}
</script>

<template>
  <SearchBar />
</template>

<style>
</style>
