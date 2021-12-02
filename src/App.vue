<template>
  <div id="app">
    <HEADER @newSearchMovies="searchMovies" @newSearchTv="searchTv"/>
    <MAIN 
    v-if="searchedWord !== undefined"
    :cardsMovies = "cardsMovies"
    :cardsTv = "cardsTv" 
    :searchedWord = "searchedWord"
    />
    <MAIN v-else />
  </div>
</template>

<script>
import axios from 'axios';
import HEADER from './components/HEADER.vue';
import MAIN from './components/MAIN.vue';
export default {
  name: 'App',
  components: {
    HEADER,
    MAIN
  },
  data(){
    return{
      cardsMovies: [],
      cardsTv: [],
      loaded: false,
      searchedWord: undefined,
    }
  },
  methods:{
    searchMovies(title){
        //chiamata Movies
        axios.get( `https://api.themoviedb.org/3/search/movie?api_key=cf3a8ad796de1dd7af76b38dc8ed5676&language=it-IT&query=${title}`)
        .then( r => {
          this.cardsMovies = r.data.results;
          this.loaded = true;
          this.searchedWord = title;
          })
        .catch( e => {
          console.log(e);
        })
        console.log('chiamata effettuata', this.cardsMovies);
    },
    searchTv(title){
      //chiamata TV Series

        axios.get( `https://api.themoviedb.org/3/search/tv?api_key=cf3a8ad796de1dd7af76b38dc8ed5676&language=it-IT&query=${title}`)
        .then( r => {
          this.cardsTv = r.data.results;
          this.loaded = true;
          this.searchedWord = title;
          })
        .catch( e => {
          console.log(e);
        })
    }
  },
  mounted(){
    this.searchTv();
    this.searchMovies();
  },
}
</script>

<style lang="scss">
#app {
  @import url('./assets/style/generals.scss');
}
</style>
