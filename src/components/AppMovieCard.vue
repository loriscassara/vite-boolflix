<!-- 
  START SCRIPT
-->

<script>

  export default {
    name: 'AppMovieCard',
    data() {
      return {
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
      <img class="wallpaper" :src="`http://image.tmdb.org/t/p/w500${film.poster_path}`" alt="wallpaper image">
    </div>

    <!-- start Card-bottom -->

    <div class="card-bottom" v-if="!active">
      <h1>{{ film.title }}</h1>
      <h5>{{ film.original_language }}</h5>
      <img class="flag" :src="`../../public/image/${film.original_language}.svg`" alt="language">
      <h3>{{ film.original_title }}</h3>
      <p>{{ film.vote_average }}</p>
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
  }

</style>