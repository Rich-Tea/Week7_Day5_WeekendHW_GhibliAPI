<template>
<div>
  <h1>Ghibli Time!</h1>
  <div class="main-container">
    <film-list :films='films'></film-list>
    <film-detail :film='selectedFilm'></film-detail>
   
   
  </div>
  </div>
</template>

<script>

import { eventBus } from './main.js';
import FilmList from './components/FilmList.vue'
import ListItem from './components/ListItem.vue'
import FilmDetail from './components/FilmDetail.vue'


export default {

  name: 'app',
  data(){
       return {
         films: [],
         selectedFilm: null
       };
     },
  components: {
     'film-detail': FilmDetail,
     'film-list': FilmList
  },
  mounted(){
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(res => res.json())
    .then(films => this.films = films)
    
    eventBus.$on('film-selected', (film) => {
      this.selectedFilm = film
    })
    
  }
}
</script>

<style>
/* .main-container {
    display: flex;
    justify-content: space-between;
} */

body {
  background-color: midnightblue;
}

h1, ul, li {
  color: goldenrod;
}

.detail-div {
  color: goldenrod;
}
</style>
