<template>
  <div class='detail-div' v-if='film'>
      <p>
          Title: {{ film.title }}
          Director: {{ film.director }} <br>
          Release date: {{ film.release_date }} <br>
          Description: {{ film.description }} <br>
          Rotten Tomatoes score: {{ film.rt_score }}
        </p>
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