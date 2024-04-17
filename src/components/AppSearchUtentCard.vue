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
    <div class="row d-flex flex-wrap g-0  p-3 gap-2">
        <div class="col-4" v-for="movie in store.movies">
            <div class="card mt-2">
              <div class="title">{{movie.title}}</div>
              <div class="orig-title">{{movie.original_title}}</div>
              <div class="lang">{{ movie.original_language }}</div>
              <div class="vote">{{ movie.vote_average }}</div>
            </div>
        </div>
    </div>
    
</template>

<style scoped lang="scss">

</style>