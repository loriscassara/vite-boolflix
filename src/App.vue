<!-- 
  START SCRIPT
-->

<script>

  import axios from 'axios'
  import { store } from './store.js'
  import AppMovieCard from './components/AppMovieCard.vue'
  import AppSearch from './components/AppSearch.vue'
  import AppSeries from './components/AppSeries.vue'

  export default {
    name: 'App',
    components: {
      AppMovieCard,
      AppSearch,
      AppSeries
    },
    data() {
      return {
        store
      }
    },
    methods: {
      getMovie() {
        if (this.store.searchInput) {
          const options = {
            method: 'GET',
            url: 'https://api.themoviedb.org/3/search/movie',
            params: { 
              query: `${this.store.searchInput}`, 
              include_adult: 'false', 
              language: 'en-US', 
              page: '1',
              api_key: 'dfb6f86f52ee328183147082281a1543'
            },
            headers: {
              accept: 'application/json',
              //authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJkZmI2Zjg2ZjUyZWUzMjgxODMxNDcwODIyODFhMTU0MyIsInN1YiI6IjY1NmRmMGEzMDg1OWI0MDBhZDM5ZjhjZCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.xe2Vb9urprdUXsWvCYsJcD5yKZmcaCCZ5LUIhgb5qyc'
            },
          };
          axios
          .request(options)
          .then(function (response) {
            store.movieList = response.data.results;
          })
          .catch(function (error) {
            //console.error(error);
          });
          const optionsSeries = {
            method: 'GET',
            url: 'https://api.themoviedb.org/3/search/tv',
            params: { 
              query: `${this.store.searchInput}`, 
              include_adult: 'false', 
              language: 'en-US', 
              page: '1',
              api_key: 'dfb6f86f52ee328183147082281a1543'
            },
            headers: {
              accept: 'application/json',
              //authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJkZmI2Zjg2ZjUyZWUzMjgxODMxNDcwODIyODFhMTU0MyIsInN1YiI6IjY1NmRmMGEzMDg1OWI0MDBhZDM5ZjhjZCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.xe2Vb9urprdUXsWvCYsJcD5yKZmcaCCZ5LUIhgb5qyc'
            }
          };
          axios
          .request(optionsSeries)
          .then(function (response) {
            store.seriesList = response.data.results;
          })
          .catch(function (error) {
            //console.error(error);
          });
        } else {
          const options = {
            method: 'GET',
            url: 'https://api.themoviedb.org/3/search/movie',
            params: { 
              query: `Marvel`, 
              include_adult: 'false', 
              language: 'en-US', 
              page: '1',
              api_key: 'dfb6f86f52ee328183147082281a1543'
            },
            headers: {
              accept: 'application/json',
              //authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJkZmI2Zjg2ZjUyZWUzMjgxODMxNDcwODIyODFhMTU0MyIsInN1YiI6IjY1NmRmMGEzMDg1OWI0MDBhZDM5ZjhjZCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.xe2Vb9urprdUXsWvCYsJcD5yKZmcaCCZ5LUIhgb5qyc'
            },
          };
          axios
          .request(options)
          .then(function (response) {
            store.movieList = response.data.results;
          })
          .catch(function (error) {
            //console.error(error);
          });
          const optionsSeries = {
            method: 'GET',
            url: 'https://api.themoviedb.org/3/search/tv',
            params: { 
              query: `Marvel`, 
              include_adult: 'false', 
              language: 'en-US', 
              page: '1',
              api_key: 'dfb6f86f52ee328183147082281a1543'
            },
            headers: {
              accept: 'application/json',
              //authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJkZmI2Zjg2ZjUyZWUzMjgxODMxNDcwODIyODFhMTU0MyIsInN1YiI6IjY1NmRmMGEzMDg1OWI0MDBhZDM5ZjhjZCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.xe2Vb9urprdUXsWvCYsJcD5yKZmcaCCZ5LUIhgb5qyc'
            }
          };
          axios
          .request(optionsSeries)
          .then(function (response) {
            store.seriesList = response.data.results;
          })
          .catch(function (error) {
            //console.error(error);
          });
        }
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

    <AppSearch @searchFilm = "getMovie" />

    <!-- start Movie Card -->

    <div class="movie-card-container">
      <AppMovieCard v-for = "movie in store.movieList" :film = "movie" />
    </div>
    <div class="movie-card-container">
      <AppSeries v-for = "series in store.seriesList" :serie = "series" />
    </div>
    
  </main>

</template>

<!-- 
  START STYLE
-->

<style scoped>

  /* start Movie Card Container */

  .movie-card-container {
    width: 80%;
    height: 60vh;
    margin: 2rem auto;
    display: flex;
    flex-wrap: nowrap;
    justify-content: space-between;
    overflow: auto;
  }

</style>