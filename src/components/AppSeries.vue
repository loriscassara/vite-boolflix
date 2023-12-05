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
    background-color: gainsboro;
    margin: 0.5rem;
    border-radius: 0.5rem;
    width: 25%;
    height: 100%;
  }

</style>