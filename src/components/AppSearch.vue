<!-- 
  START SCRIPT
-->

<script>

  import { store } from '../store.js'

  export default {
    name: 'AppSearch',
    emits: ['searchFilm'],
    data() {
      return {
        store
      }
    },
    methods: {
      getInput() {
        this.$emit('searchFilm');
      },
    },
  }

</script>

<!-- 
  START TEMPLATE
-->

<template>

  <!-- start Header -->

  <header>
    <img id="logo" src="../../public/image/netflix-mobile-application-logo-free-png.webp" alt="logo">
    <input type="text" placeholder="Cerca.." v-model="store.searchInput" @keyup="getInput">
  </header>

</template>

<!-- 
  START STYLE
-->

<style scoped>

  /* start Header */

  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 2rem;
    background-color: black;
  }

  /* start logo */

  #logo {
    height: 4rem;
    margin: 0.5rem;
  }

</style>