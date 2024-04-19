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
        
                <div class="card" style="width: 18rem;">
                    <div v-if="cardInfo.title" class="title">{{cardInfo.title }}</div>
                    <div v-else>{{ cardInfo.name }}</div>
                    <div v-if="cardInfo.original_title" class="orig-title">{{cardInfo.original_title }}</div>
                    <div v-else>{{ cardInfo.original_name }}</div>
                    <img v-if="flagsArray.includes(cardInfo.original_language)" :src="getFlagUrl(cardInfo)" :alt="cardInfo.original_language">
                    <div v-else>{{ cardInfo.original_language  }}</div>
                    <div class="vote">{{ Math.ceil(cardInfo.vote_average / 2) }}</div>
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