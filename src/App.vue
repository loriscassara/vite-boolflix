<!-- 
  START SCRIPT
-->

<script>

  import axios from 'axios'
  import store from './store.js'
  import AppMovieCard from './components/AppMovieCard.vue'
  import AppSearch from './components/AppSearch.vue'

  export default {
    name: 'App',
    components: {
      AppMovieCard,
      AppSearch
    },
    data() {
      return {
        store
      }
    },
    methods: {
      getMovie() {
        const options = {
          method: 'GET',
          url: 'https://api.themoviedb.org/3/search/movie',
          params: { 
            query: 'future', 
            include_adult: 'false', 
            language: 'en-US', 
            page: '1' 
          },
          headers: {
            accept: 'application/json',
            authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJkZmI2Zjg2ZjUyZWUzMjgxODMxNDcwODIyODFhMTU0MyIsInN1YiI6IjY1NmRmMGEzMDg1OWI0MDBhZDM5ZjhjZCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.xe2Vb9urprdUXsWvCYsJcD5yKZmcaCCZ5LUIhgb5qyc'
          }
        };
        axios
        .request(options)
        .then(function (response) {
          //console.log(response.data.results);
          store.movieList = response.data.results;
        })
        .catch(function (error) {
          //console.error(error);
        });
      }
    },
    mounted() {
      this.getMovie()
    }
  }

</script>

<!-- 
  START TEMPLATE
-->

<template>

  <!-- start main -->

  <main>

    <!-- start input Search -->

    <AppSearch />

    <!-- start Movie Card -->

    <div class="movie-card-container">
      <AppMovieCard v-for = "movie in store.movieList" :film = "movie" />
    </div>  
  
  </main>

</template>

<!-- 
  START STYLE
-->

<style scoped>

  /* start Movie Card Container */

  .movie-card-container {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-between;
    margin: 0 auto;
    width: 85%;
  }

</style>