<template>
    <div class="modal fixed inset-0 flex items-center justify-center bg-slate-600/75">
        <div class="modal-inner w-full lg:w-1/2 bg-white flex relative">
            <img
             class="w-96"
             :src="movie.Poster" :alt="movie.Title">
            <div class="p-6">
                <h1 class="text-2xl font-bold mb-4">{{ movie.Title }} - {{ movie.Released }}</h1>
                <ul>
                    <li><strong>Actors: </strong> {{ movie.Actors }}</li>
                    <li><strong>Director: </strong>{{ movie.Director }}</li>
                </ul>
                <p class="mt-4">{{ movie.Plot }}</p>
            </div>
            <a href="" id="close" class="absolute top-0 right-0 bg-slate-700" @click.prevent="closeModal">
                <svg viewBox="0 0 24 24" focusable="false" height="24" width="24" jsname="lZmugf" class="fill-white">
                    <path d="M0 0h24v24H0z" fill="none"></path>
                    <path d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12z"></path>
                </svg>
            </a>
        </div>
        
    </div>
</template>

<script>
   export default { 
        name: 'FooterElm',
        props: ['movie'],
        data(){
            return {
                
            }
        },
        methods: {
            closeModal(){
                this.$emit('close-modal');
            }
        },
   }    

</script>

<style scoped>

</style>