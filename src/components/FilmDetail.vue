<template>
  <div>
      <ul>
        <li v-for="(film, index) in film" :film="film" :key="index">
          Director: {{ film.director }} <br>
          Release date: {{ film.release_date }} <br>
          Description: {{ film.description }} <br>
          Rotten Tomatoes score: {{ film.rt_score }}
        </li>
      </ul>
      
  </div>
</template>

<script>
import { eventBus } from '../main.js'
import FilmList from './FilmList.vue'

export default {
      name: 'film-detail',
      props: ['film']
}
</script>

<style>

</style>