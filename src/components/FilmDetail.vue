<template>
  <div class='detail-div' v-if='film'>
      <h2> {{ film.title }}</h2> 
         <h3> Director: {{ film.director }}</h3>
         <h3>Release date: {{ film.release_date }} </h3> 
         <h3>Description: {{ film.description }} </h3> 
        <h3> Rotten Tomatoes score: {{ film.rt_score }} </h3>
     </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
      name: 'film-detail',
      props: ['film']
}
</script>

<style>

</style>