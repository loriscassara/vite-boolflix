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

  <div class="card-container">

    <!-- start Card-top -->

    <div class="card-top">
      <img class="wallpaper" :src="`http://image.tmdb.org/t/p/w500${serie.poster_path}`" alt="wallpaper image">
    </div>

    <!-- start Card-bottom -->
    
    <div class="card-bottom">
      <h1>{{ serie.name }}</h1>
      <h5>{{ serie.original_language }}</h5>
      <img class="flag" :src="`../../public/image/${serie.original_language}.svg`" alt="image language">
      <h3>{{ serie.original_name }}</h3>
      <p>{{ serie.popularity }}</p>
    </div>
  </div>

</template>

<!-- 
  START STYLE
-->

<style scoped>

  /* start CardS Container */
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
    opacity: 0;
    transition: all .55s ease;
  }

  .card-bottom:hover { opacity: 1; }

  /* start Flag */

  .flag {
    width: 10%;
    margin: 0.5rem;
  }

  /* start Wallpaper */

  .wallpaper {
    height: 100%;
    width: 100%;
    border-radius: 0.5rem;
  }

  /* start image language */

  img {
    width: 10%;
  }

  /* start h1 */

  h1 {
    padding-bottom: 0.5rem;
  }

</style>