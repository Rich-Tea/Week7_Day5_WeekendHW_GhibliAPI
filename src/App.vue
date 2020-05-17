<template>
  <div class="main-container">
    <h1>Ghibli Taimu</h1>
    <film-list :films='films'></film-list>
    <film-detail :film='films'></film-detail>
   
   
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
    
    
  }
}
</script>

<style>

</style>
