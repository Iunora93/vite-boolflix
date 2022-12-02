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
  padding-top: 50px;
  input{
    margin-right: 20px;
    border: none;
    border-radius: 5px;
    padding: 10px;    
  }
  button{
    border: 2px solid white;
    border-radius: 5px;
    padding: 10px;
    background-color: black;   
    color: white; 
  }
}

</style>
