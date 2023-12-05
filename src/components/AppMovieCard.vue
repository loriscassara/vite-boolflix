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
    <h1>{{ film.title }}</h1>
    <h5>{{ film.original_language }}</h5>
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
    width: 25%;
    background-color: gainsboro;
    margin: 0.5rem;
    min-height: 18rem;
    border-radius: 0.5rem;
  }

</style>