<template>
  <!-- Header -->
  <header-elm class="bg-slate-500 text-white py-6"></header-elm>

  <!-- Content -->
  <featured-movie></featured-movie>
  <movie-search @movie-result="ShowMovieResult"></movie-search>
  <search-result :movies="MovieResult"></search-result>

  <!-- Footer -->
  <footer-elm></footer-elm>
</template>

<script>

  import HeaderElm from './components/HeaderElm.vue';
  import FooterElm from './components/FooterElm.vue';
  import MovieSearch from './components/MovieSearch.vue';
  import SearchResult from './components/SearchResult.vue';

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
    }
  },
  methods: {
    ShowMovieResult(movies){
        //console.table(movies);
        this.MovieResult = movies;
    }
  },
  watch: {
    MovieResult(){
        console.log('changed');
    }
  }
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
