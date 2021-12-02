<template>
  <main>
    <div class="card-box movies">
      <Card 
      v-for="(card, index) in cards" 
      :key="index" 
      :title="card.title"
      :originalTitle="card.original_title"
      :language="card.original_language"
      :vote="card.vote_average"
      :cat="cat"
      :name="card.name"
      :originalName="card.original_name"
      />
      
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
    cards: Array,
    cat: String,
  },
  
}
</script>

<style lang="scss">
@import url('../assets/style/generals.scss');
@import url('../assets/style/vars.scss');
main{
  width: 100%;
  min-height: calc(100vh - 90px);
  background-color: #D91921;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  .card-box{
    height: 500px;
    overflow: auto;
    width: 80%;
    margin: 5px auto;
    background-color: black;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    color: white;
    padding: 15px;
  }
}

</style>