<template>
	<div>
		<form @submit.prevent="SearchMovie" class="text-center my-10">
				<input class="border-2 border-slate-400 p-4 w-96" type="text" v-model="search" placeholder="Type movie title here...">
				<button type="submit" class="bg-slate-600 text-white px-8 py-4 border-2 border-slate-600 ml-4">Search</button>
		</form>
	</div>
</template>

<script>
	import env from '../env.js';

export default {
	name: "MovieSearch",
	created() {},
	emtis: ['movies'],
	data() {
		return {
			search: '',
			loading: false
		}
	},
	props: {},
	methods: {
		SearchMovie(){
				if(this.search != ''){
					fetch(`http://www.omdbapi.com/?apikey=${env.apikey}&s=${this.search}`)
					.then(response => response.json())
					.then(data => {
								const movies = data.Search;
								const loading = false;
								this.$emit('movie-result', movies, loading);
								this.search = '';
								this.loading = false;
								//console.log(movies)
					});
				}
				
		}
	},
	watch: {
		search(){
			if(this.search != ''){
				this.loading = true;
			}else{
				this.loading = false;
			}
			this.$emit('loading-result', this.loading);
		}
	}
};
</script>

<style scoped></style>