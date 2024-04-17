<script>
import {store} from '../store.js'
export default {
    name: 'AppSelect',
   data () {
    return {
        store
    }
   }
}
</script>

<template>
    <div class="p-2">
            <input v-model="store.utentSelect" class="mx-2">
            <button @click="$emit('searchDone')"> clicca</button>
    </div>
</template>
        
        


<style scoped lang="scss">
</style>
