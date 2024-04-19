<script>

import AppHeader from './components/AppHeader.vue'
import AppSearchList from './components/AppSearchList.vue'
import AppSelect from './components/AppSelect.vue'
import {store} from './store.js'
import axios from 'axios'

export default {
  components : {
    AppHeader,
    AppSelect,
    AppSearchList
    

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
    <h1>Film</h1>
    <AppSearchList  v-for="movie in store.movies" :key="movie.id" :cardInfo="movie"></AppSearchList>
    <h1>Serie Tv</h1>
    <AppSearchList  v-for="series in store.series" :key="series.id" :cardInfo="series"></AppSearchList>
  </main>
</template>

<style lang="scss">
 @use './style/generic' ;
</style>
