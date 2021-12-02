<template>
  <div id="app">
    <HEADER @newSearch="searchTitle"/>
    <MAIN 
    v-if="searchedWord !== undefined"
    :cards = "cards"
    :cat = "cat" 
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
      cards: [],
      loaded: false,
      searchedWord: undefined,
      cat: ' ',
    }
  },
  methods:{
    searchTitle(title, cat){
      axios.get( `https://api.themoviedb.org/3/search/${cat}?api_key=cf3a8ad796de1dd7af76b38dc8ed5676&language=it-IT&query=${title}`)
        .then( r => {
          this.cards = r.data.results;
          this.loaded = true;
          this.searchedWord = title;
          console.log('hai ricevuto la parola da header', title);
          console.log('hai ricevuto la cat da header', cat);
          console.log('ora la lunghezza dell\'array è', this.cards.length);
          this.cat = cat;
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
