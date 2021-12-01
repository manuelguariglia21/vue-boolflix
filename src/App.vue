<template>
  <div id="app">
    <HEADER />
    <MAIN />
    <div>{{cards.length}}</div>
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
      apiUrl: 'https://api.themoviedb.org/3/search/movie?api_key=cf3a8ad796de1dd7af76b38dc8ed5676&language=it-IT&query=scarface',
      loaded: false,

    }
  },
  methods:{
    getApi(){
      axios.get(this.apiUrl)
        .then( r => {
          this.cards = r.data.results;
          this.loaded = true;
        })
        .catch( e => {
          console.log(e);
        })
    },
  },
  mounted(){
    this.getApi();
  },
}
</script>

<style lang="scss">
#app {
  @import url('./assets/style/generals.scss');
}
</style>
