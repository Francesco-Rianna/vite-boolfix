<script>
import { store } from '../store.js'

export default {
    name: 'AppSearchList',
    props : {
        cardInfo : Object
    },
    data() {
        return {
            store,
            flagsArray: ['it', 'en', 'fr']
        }
    },
    methods: {
        getFlagUrl(cardInfo) {
            let flagUrl =cardInfo.original_language + '.svg';
            return `../src/assets/img/${flagUrl}`;
        },
    }
}
</script>

<template>
    <div>
        <div class="row d-flex flex-wrap g-0 p-3 gap-4 ">
            <div class="col-4 ">
                <div class="card mt-2">
                    <div class="title">{{cardInfo.title }}</div>
                    <div class="orig-title">{{cardInfo.original_title }}</div>
                    <img :src="getFlagUrl(cardInfo)" :alt="cardInfo.original_language">
                    <div class="vote">{{ Math.ceil(cardInfo.vote_average / 2) }}</div>
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