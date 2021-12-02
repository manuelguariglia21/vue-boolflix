<template>
  <main>
    <div v-if="cardsMovies.length > 0" class="card-box movies">
      <Card 
      v-for="card in cardsMovies" 
      :key="card.id" 
      :title="card.title"
      :originalTitle="card.original_title"
      :language="card.original_language"
      :vote="card.vote_average"
      :name="card.name"
      :originalName="card.original_name"
      :image="card.poster_path"
      />
      
    </div>

    <div v-if="cardsTv.length > 0" class="card-box tv">
      <Card 
      v-for="card in cardsTv" 
      :key="card.id" 
      :title="card.name"
      :originalTitle="card.original_name"
      :language="card.original_language"
      :vote="card.vote_average"
      :name="card.name"
      :originalName="card.original_name"
      :image="card.poster_path"
      />
      
    </div>

    <div v-else class="card-box">
      <h2>Ci spiace, non ci sono risultati per : "{{searchedWord}}".</h2>
    </div>
  </main>
</template>

<script>
import Card from './Card.vue';
export default {
  name: 'MAIN',
  components: {
    Card
  },
  props:{
    cardsMovies: Array,
    cardsTv: Array,
    searchedWord: String,
  },
  
}
</script>

<style lang="scss">
@import url('../assets/style/generals.scss');
@import url('../assets/style/vars.scss');
main{
  width: 100%;
  min-height: calc(100vh - 90px);
  background-color: black;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  .card-box{
    height: 500px;
    overflow: auto;
    width: 80%;
    margin: 5px auto;
    background-color: #141414;
    box-shadow: 2px 5px 4px 5px black;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    color: white;
    padding: 15px;
    margin-bottom: 15px;
  }
}

</style>