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
    width: 23%;
    margin: 0.5rem;
    background-color: rgb(128, 126, 126);
    border-radius: 0.5rem;
  }

</style>