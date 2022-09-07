<template>
  <div class="container mx-auto">
    <div class="movie-container">
        <div v-for="movie in movies" :key="movie.imdbID" class="overflow-hidden single-movie w-1/5 px-2 mb-6 relative">
          <img :src="movie.Poster" :alt="movie.Title">
          <h3 class="bottom-6 text-white bg-sky-900/100 p-2 w-full">{{ movie.Title }} - <span>{{ movie.Year }}</span></h3>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SearchResult",
  created() {},
  data() {
    return {};
  },
  props: ['movies'],
  methods: {},
};
</script>

<style scoped>
    .movie-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-evenly;
  }
</style>