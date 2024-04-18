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
            <input v-model="store.utentSelect" class="mx-2 bg-transparent p-1">
            <button @click="$emit('searchDone')" class="bg-transparent rounded py-1 px-4"> Cerca</button>
    </div>
</template>
        
        


<style scoped lang="scss">
input,button{
    color:white;
}
</style>
