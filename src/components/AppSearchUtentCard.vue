<script>
import { store } from '../store.js'

export default {
    name: 'AppSearchUtent',
    data() {
        return {
            store,
            flagsArray: ['it', 'en', 'fr']
        }
    },
    methods: {
        getFlagUrl(movie) {
            let flagUrl = movie.original_language + '.svg';
            return `../src/assets/img/${flagUrl}`;
        },
        getFlagUrlSeries(series) {
            let flagUrlSeries = series.original_language + '.svg';
            return `../src/assets/img/${flagUrlSeries}`;
        }
    }
}
</script>

<template>
    <div>
        <h1 class="p-3">FILM</h1>
        <div class="row d-flex flex-wrap g-0 p-3 gap-4 justify-content-center">
            <div class="col-4" v-for="movie in store.movies" :key="movie.id">
                <div class="card mt-2">
                    <div class="title">{{ movie.title }}</div>
                    <div class="orig-title">{{ movie.original_title }}</div>
                    <img :src="getFlagUrl(movie)" :alt="movie.original_language">
                    <div class="vote">{{ Math.ceil(movie.vote_average / 2) }}</div>
                </div>
            </div>
        </div>

        <h1>Series</h1 class="p-3">
        <div class="row d-flex flex-wrap g-0 p-3 gap-4 justify-content-center">
            <div class="col-4" v-for="series in store.series" :key="series.id">
                <div class="card mt-2">
                    <div class="title">{{ series.name }}</div>
                    <div class="orig-title">{{ series.original_name }}</div>
                    <img :src="getFlagUrlSeries(series)" :alt="series.original_language">
                    <div class="vote">{{ Math.ceil(series.vote_average / 2) }}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
img {
    width: 35px;
} h1{
    color: red;
}
</style>