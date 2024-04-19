<script>

import AppHeader from './components/AppHeader.vue'
import AppSearchUtentCard from './components/AppSearchUtentCard.vue'
import AppSelect from './components/AppSelect.vue'
import {store} from './store.js'
import axios from 'axios'

export default {
  components : {
    AppHeader,
    AppSelect,
    AppSearchUtentCard
    

  },
  data(){
    return {
      store
    }
  }, 
  methods :{
    getMovieFromApi(){
      const queryParams = {
        query : store.utentSelect
      }
      
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=4ade3b6132e6d33d867aa235b91353ee',{
        params:queryParams
      })
      .then((response)=>{
       store.movies= response.data.results
       
      })

    },

    getSeriesFromApi(){
      const queryParams = {
        query : store.utentSelect
      }
      
      axios.get('https://api.themoviedb.org/3/search/tv?api_key=4ade3b6132e6d33d867aa235b91353ee',{
        params:queryParams
      })
      .then((response)=>{
       store.series= response.data.results
       
      })

    }
  },
  mounted(){
    this.getMovieFromApi();
    this.getSeriesFromApi() ;
  }
}

</script>

<template>
  <header class="d-flex justify-content-between px-3 py-1">
    <AppHeader></AppHeader>
    <AppSelect @searchDoneMovie="getMovieFromApi" @searchDoneSeries="getSeriesFromApi"></AppSelect>
    
  </header>

  <main>
    <AppSearchUtentCard></AppSearchUtentCard>
  </main>
</template>

<style lang="scss">
 @use './style/generic' ;
</style>
