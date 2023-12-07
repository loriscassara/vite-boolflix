<!-- 
  START SCRIPT
-->

<script>

  export default {
    name: 'AppMovieCard',
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

  <div class="card-container">
    <img class="wallpaper" :src="`http://image.tmdb.org/t/p/w500${film.poster_path}`" alt="poster image">
    <h1>{{ film.title }}</h1>
    <h5>{{ film.original_language }}</h5>
    <img :src="`../../public/image/${serie.original_language}.svg`" alt="language">
    <h3>{{ film.original_title }}</h3>
    <p>{{ film.vote_average }}</p>
  </div>

</template>

<!-- 
  START STYLE
-->

<style scoped>

  /* start Card */

  .card-container {
    width: 23%;
    height: 85%;
    margin: 0.5rem;
    background-color: rgb(128, 126, 126);
    border-radius: 0.5rem;
    flex-shrink: 0;
    overflow-x: auto;
  }

  /* start Wallpaper */

  .wallpaper {
    width: 100%;
  }

  /* start image language */

  img {
    width: 10%;
  }

</style>