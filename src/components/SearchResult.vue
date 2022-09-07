<template>
  <div class="container mx-auto">
    <div class="border border-slate-300 shadow p-4 w-full mx-auto mb-4" v-if="loading">
      <div class="animate-pulse flex space-x-4">
        <div class="rounded-full bg-slate-200 h-10 w-10"></div>
        <div class="flex-1 space-y-6 py-1">
          <div class="h-2 bg-slate-200 rounded"></div>
          <div class="space-y-3">
            <div class="grid grid-cols-3 gap-4">
              <div class="h-2 bg-slate-200 rounded col-span-2"></div>
              <div class="h-2 bg-slate-200 rounded col-span-1"></div>
            </div>
            <div class="h-2 bg-slate-200 rounded"></div>
          </div>
        </div>
      </div>
    </div>
    <div class="movie-container">
        <div v-for="movie in movies" :key="movie.imdbID" class="overflow-hidden single-movie w-1/5 px-2 mb-6 relative">
          <a href="#" id="" @click.prevent="movieDetail(movie.imdbID)">
          <img :src="movie.Poster" :alt="movie.Title">
          <h3 class="bottom-6 text-white bg-sky-900/100 p-2 w-full">{{ movie.Title }} - <span>{{ movie.Year }}</span></h3>
          </a>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SearchResult",
  created() {},
  data() {
    return {
      
    };
  },
  props: ['movies','loading'],
  methods: {
    movieDetail(id){
      this.$emit('movie-details', id);
    }
  },
};
</script>

<style scoped>
    .movie-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-evenly;
  }
</style>