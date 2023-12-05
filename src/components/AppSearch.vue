<!-- 
  START SCRIPT
-->

<script>

  import { store } from '../store.js'
  import axios from 'axios'

  export default {
    name: 'AppSearch',
    data() {
      return {
        store
      }
    },
    methods: {
      getInput() {
        this.getMovie()
      },
      getMovie() {
        const options = {
          mothod: 'GET',
          url: 'https://api.themoviedb.org/3/search/movie',
          params: { query: `${this.store.searchString}`, include_adult: 'false', language: 'en-US', page: '1' },
          headers: {
            accept: 'application/json',
            authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJkZmI2Zjg2ZjUyZWUzMjgxODMxNDcwODIyODFhMTU0MyIsInN1YiI6IjY1NmRmMGEzMDg1OWI0MDBhZDM5ZjhjZCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.xe2Vb9urprdUXsWvCYsJcD5yKZmcaCCZ5LUIhgb5qyc'
          }
        };
        axios
        .request(options)
        .then(function (response) {
          store.movieList = response.data.results;
        })
        .catch(function (error) {
          //console.log(error);
        });
      }
    },
  }

</script>

<!-- 
  START TEMPLATE
-->

<template>

  <!-- start input Search -->

  <input type="text" placeholder="Cerca.." v-model = "store.searchInput" @keyup = "getInput">
  <button @click = "getInput">Cerca</button>

</template>

<!-- 
  START STYLE
-->

<style scoped>

  

</style>