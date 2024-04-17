<script>

import AppHeader from './components/AppHeader.vue'
import {store} from './store.js'
import axios from 'axios'

export default {
  components : {
    AppHeader,
    

  },
  data(){
    return {
      store
    }
  }, 
  methods :{
    getMovieFromApi(){
      const queryParams = {}
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=4ade3b6132e6d33d867aa235b91353ee',{
        params:queryParams
      })
      .then((response)=>{
       store.movies= response.data.result
       console.log(store.movies)
      })

    }
  },
  mounted(){
    this.getMovieFromApi();
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
