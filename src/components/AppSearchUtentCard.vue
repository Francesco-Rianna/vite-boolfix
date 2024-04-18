<script>
    import { store } from '../store.js'
    export default {
        name: 'AppSearchUtent',
        data(){
            return{
                store
            }
        }
    }
</script>

<template>
    <div class="row d-flex flex-wrap g-0  p-3 gap-4 justify-content-center">
        <div class="col-4" v-for="movie in store.movies">
            <div class="card mt-2">
              <div class="title">{{movie.title}}</div>
              <div class="orig-title">{{movie.original_title}}</div>
              <img :src="`src/assets/img/${movie.original_language}.svg`" :alt=" movie.original_language " >
              
              <div class="vote">{{ movie.vote_average }}</div>
            </div>
        </div>
    </div>
    
</template>

<style scoped lang="scss">
img {
    width: 35px;
}

</style>