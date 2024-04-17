<script>

import AppHeader from './components/AppHeader.vue'
import {store} from './store.js'

export default {
  components : {
    AppHeader,
    

  },
  data(){
    return {
      store
    }
  }, 
  metodhs :{
   
  }
}

</script>

<template>
  <header class="">
    <AppHeader></AppHeader>
    
  </header>
</template>

<style lang="scss">
 @use './style/generic' ;
</style>
