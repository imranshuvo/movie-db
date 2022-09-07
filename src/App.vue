<template>
  <!-- Header -->
  <header-elm class="bg-slate-500 text-white py-6"></header-elm>

  <!-- Content -->
  <!-- <featured-movie></featured-movie> -->
  <movie-search @movie-result="ShowMovieResult" @loading-result="ShowLoading"></movie-search>
  <search-result @movie-details="showDetails" :movies="MovieResult" :loading="loading" :responseText="responseText"></search-result>

  <!-- Footer -->
  <footer-elm :movie="movie" v-if="showModal" @close-modal="closeModal"></footer-elm>
</template>

<script>

  import HeaderElm from './components/HeaderElm.vue';
  import FooterElm from './components/FooterElm.vue';
  import MovieSearch from './components/MovieSearch.vue';
  import SearchResult from './components/SearchResult.vue';
  import env from './env.js';

export default {
  name: 'App',
  components: {
    HeaderElm,
    FooterElm,
    MovieSearch,
    SearchResult
  },
  data() {
    return {
      MovieResult: [],
			responseText: '',
      loading: false,
      movie: {},
			showModal: false
    }
  },
  methods: {
    ShowMovieResult(movies, response ){
        //console.table(movies);
        this.MovieResult = movies;
				this.responseText = response;

				console.log(this.responseText);
    },
    ShowLoading(loading){
      this.loading = loading;
    },
    showDetails(id){
       fetch(`http://www.omdbapi.com/?apikey=${env.apikey}&i=${id}`)
       .then( response => response.json())
       .then( data => {
          this.movie = data;
					this.showModal = true;
       });
    },
		closeModal(){
			this.showModal = false;
		}
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
* {
  margin: 0;
  padding: 0;
  
}
</style>
