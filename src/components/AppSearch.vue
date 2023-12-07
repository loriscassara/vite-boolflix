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

  <!-- start input Search -->

  <input type="text" placeholder="Cerca.." v-model = "store.searchInput" @keyup = "getInput">
  <select name="language" id="language" v-model = "store.currentLanguage">
    <option value="all">All</option>
    <option value="en">English</option>
    <option value="it">Italian</option>
  </select>

</template>

<!-- 
  START STYLE
-->

<style scoped>

  

</style>