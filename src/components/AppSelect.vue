<script>
import { store } from '../store.js'

export default {
    name: 'AppSelect',
    data() {
        return {
            store
        }
    },
    methods: {
        emitSearchBoth() {
            this.$emit('searchDoneMovie');
            this.$emit('searchDoneSeries');
        }
    }
}
</script>

<template>
    <div class="p-2">
        <input  @keyup.enter="emitSearchBoth" v-model="store.utentSelect" class="mx-2 bg-transparent p-1">
        <button @click="emitSearchBoth" class="bg-transparent rounded py-1 px-4"> Cerca</button>
    </div>
</template>

<style scoped lang="scss">
input, button {
    color: white;
}
</style>