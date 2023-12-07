<!-- 
  START SCRIPT
-->

<script>

  import { store } from '../store.js'

  export default {
    name: 'AppMovieCard',
    data() {
      return {
        store,
        active: true
      }
    },
    props: {
      film: ''
    },
  }

</script>

<!-- 
  START TEMPLATE
-->

<template>

  <!-- start Card -->

  <div class="card-container" @mouseenter="active = false" @mouseleave="active = true">

    <!-- start Card-top -->

    <div class="card-top">
      <img class="wallpaper" v-if="film.poster_path" :src="`http://image.tmdb.org/t/p/w500${film.poster_path}`" alt="wallpaper image">
      <img class="wallpaper" v-else src="../../public/image/image-not-available.jpg" alt="wallpaper image">
    </div>

    <!-- start Card-bottom -->

    <div class="card-bottom" v-if="!active">
      <h1>{{ film.title }}</h1>
      <h5>Lingua:</h5><span v-if="!this.store.lingue.includes(film.original_language)">{{ film.original_language }}</span>
      <img class="flag" :src="`../../public/image/${film.original_language}.svg`" alt="language">
      <h3>Titolo:</h3><span>{{ film.original_title }}</span>
      <h3>Votazione:</h3><span>{{ film.vote_average }}</span>
      <h3>View:</h3><span>{{ film.overview }}</span>
    </div>
  </div>

</template>

<!-- 
  START STYLE
-->

<style scoped>

  /* start Card */

  .card-container {
    width: 18rem;
    height: 50vh;
    margin: 0 0.5rem;
    flex-shrink: 0;
    position: relative;
  }

  /* start Card-top */

  .card-top {
    height: 100%;
  }

  /* start Card-bottom */

  .card-bottom {
    background-color: rgba(122, 122, 122, 0.79);    
    position: absolute;
    top: 0;
    border-radius: 0.5rem;
    width: 100%;
    height: 100%;
    overflow: auto;
    padding: 0.5rem;
  }

  /* start Flag */

  .flag {
    width: 10%;
    margin: 0.5rem;
  }

  /* start Wallpaper */

  .wallpaper {
    width: 100%;
    height: 100%;
    border-radius: 0.5rem;
  }

  /* start image language */

  img {
    width: 10%;
  }

  /* start h1 title */

  h1 {
    padding-bottom: 0.5rem;
    text-align: center;
  }

</style>