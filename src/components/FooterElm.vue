<template>
    <div class="modal absolute inset-0 flex items-center justify-center bg-slate-600/75" v-if="!modalClosed">
        <div class="modal-inner w-full lg:w-1/2 bg-white flex relative">
            <img
             class="w-96"
             :src="movie.Poster" :alt="movie.Title">
            <div class="p-6">
                <h1 class="text-2xl font-bold mb-4">{{ movie.Title }}</h1>
                <ul>
                    <li><strong>Actors: </strong> {{ movie.Actors }}</li>
                    <li><strong>Director: </strong>{{ movie.Director }}</li>
                    <li><strong>Released: </strong>{{ movie.Released }}</li>
                </ul>
                <p class="">{{ movie.Plot }}</p>
            </div>
            <a href="#" id="close" class="absolute top-0 right-0" @click.prevent="closeModal">X</a>
        </div>
        
    </div>
</template>

<script>
   export default { 
        name: 'FooterElm',
        props: ['movie','modalClosed'],
        data(){
            return {
                closeTheModal: false,
            }
        },
        methods: {
            closeModal(){
                this.closeTheModal = !this.closeTheModal;
            }
        },
        computed: {
        
        }

   }    

</script>

<style scoped>

</style>