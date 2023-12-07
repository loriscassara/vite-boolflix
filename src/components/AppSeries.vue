<!-- 
  START SCRIPT
-->

<script>

  export default {
    name: 'AppSeries',
    props: {
      serie: ''
    }
  }

</script>

<!-- 
  START TEMPLATE
-->

<template>

  <!-- start CardS Container -->

  <div class="cardS">
    <h1>{{ serie.name }}</h1>
    <h5>{{ serie.original_language }}</h5>
    <img :src="`../../public/image/${serie.original_language}.svg`" alt="image language">
    <h3>{{ serie.original_name }}</h3>
    <p>{{ serie.popularity }}</p>
  </div>

</template>

<!-- 
  START STYLE
-->

<style scoped>

  /* start CardS Container */
  .cardS {
    width: 23%;
    height: 85%;
    margin: 0.5rem;
    background-color: rgb(128, 126, 126);
    border-radius: 0.5rem;
    flex-shrink: 0;
    overflow-x: auto;
  }

  /* start image language */

  img {
    width: 10%;
  }

</style>