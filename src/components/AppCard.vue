<script>

import "/node_modules/flag-icons/css/flag-icons.min.css";

export default {
  name: 'AppCard',
  
  props: {
    details : Object,
  },
  methods: {
    getFlag(lang) {
      if (lang === "en") {
        return "gb";
      } else if (lang === "ko") {
        return "kr";
      } else return lang;
    },
    vote(details) {
      return Math.ceil(details.vote_average / 2);
    },
  },
}
</script>

<template>
  <div class="series-card">
    <div class="list-container">
      <ul>
        <li> <span>Titolo: {{details.name}}{{details.title}}</span></li>
          <li v-if="(details.name != details.original_name || details.title != details.original_title)">Titolo originale: {{ details.original_name }}{{details.original_title}}</li>
          <li><span :class="`fi fi-${getFlag(details.original_language)}`"></span></li>
          <li>Voto: 
            <i class="fa-solid fa-star" v-for="n in vote(details)"></i>
            <i class="fa-regular fa-star" v-for="n in (5 - vote(details))"></i>        
          </li>
          <div class="overview">
            <li>Overview: {{details.overview}}</li>
          </div>
        </ul>
    </div>
    <img :src="`https://image.tmdb.org/t/p/w342${details.poster_path}`" alt="">    
  </div>
</template>

<style lang="scss" scoped>
.series-card{
  position: relative;
  width: 300px;
  height: auto;
  margin: 50px 0 30px 0;
  &:hover .list-container{
    display: block;
  }
  .list-container{
    display: none;
    height: 100%;
    width: 100%;
    background-color: rgba($color: #000000, $alpha: 0.8);
    position: absolute;
    bottom: 0;
    left: 0;
    border: 5px solid white;
    
      
    ul{
      transform: translateY(-50%);
      position: absolute;
      top: 50%;
      left: 0;
      right: 0;
      padding: 10px;     
      list-style: none;
      height: 100%;
      overflow-y: auto;
      overflow-y: hidden;
      li{
        padding: 5px;
        text-align: center;
        color: white; 
        font-size: 14px;       
        i{
          color: yellow;
        }
        
      }
      .overview{
          font-size: 12px;
          max-height: 100%;
        }
    }
  }
  img{
    display: block;
    max-width: 100%;
  }
}
</style>