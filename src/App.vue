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
    .catch(error => console.log(error));

    
    eventBus.$on('film-selected', (film) => {
      this.selectedFilm = film
    })
    
  }
}
</script>

<style>
.main-container {
    display: grid;
    grid-template-columns: 1fr 200px 1fr;
    grid-template-rows: 1fr;
    grid-column-gap: 20px;
    grid-row-gap: 20px;
    justify-items: stretch;
    align-items: stretch;
 
}

body {
  background-color: midnightblue;
  border: 10px;
}

h1 {
  color: goldenrod;
  text-align: center;
  font-size: 3em;
  font-family: Marker Felt, fantasy;
}

ul, li {
  color: goldenrod;
  font-weight: bold;
  font-size: 20px;
  font-family: Marker Felt, fantasy;
}

.detail-div {
  color: goldenrod;
  font-family: Marker Felt, fantasy;
   font-weight: bold;
}
</style>
