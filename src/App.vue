<template>
  <div id="app">
    <HEADER @newSearch="searchTitle"/>
    <MAIN v-if="searchedWord !== undefined"
    :cards = "cards"/>
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
      cards: [],
      loaded: false,
      searchedWord: undefined,
    }
  },
  methods:{
    searchTitle(title){
      axios.get( `https://api.themoviedb.org/3/search/movie?api_key=cf3a8ad796de1dd7af76b38dc8ed5676&language=it-IT&query=${title}`)
        .then( r => {
          this.cards = r.data.results;
          this.loaded = true;
          this.searchedWord = title;
          console.log('hai ricevuto la parola da header', title);
          console.log('ora la lunghezza dell\'array è', this.cards.length);
        })
        .catch( e => {
          console.log(e);
        })
    },
  },
  mounted(){
    this.searchTitle();
  },
}
</script>

<style lang="scss">
#app {
  @import url('./assets/style/generals.scss');
}
</style>
