<template>
  <div>
      <ul>
        <li v-for="(film, index) in film" :film="film" :key="index">
          {{ film.director }} <br>
          {{ film.release_date }} <br>
          {{ film.description }} <br>
          {{ film.rt_score }}
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