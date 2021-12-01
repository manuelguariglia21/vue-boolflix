<template>
  <main>
    <div class="card-box">
      <Card />
      <Card />
      <Card />
      <Card />
      <Card />
      <Card />
      <Card />
      <Card />
      <Card />
      <Card />
      <Card />
      <Card />
      <Card />
      <Card />
    </div>
  </main>
</template>

<script>
import Card from './Card.vue';
export default {
  name: 'MAIN',
  components: {
    Card
  }
}
</script>

<style lang="scss">
@import url('../assets/style/generals.scss');
@import url('../assets/style/vars.scss');
main{
  width: 100%;
  height: calc(100vh - 90px);
  background-color: #D91921;
  display: flex;
  align-items: center;
  justify-content: center;
  .card-box{
    height: 500px;
    overflow: auto;
    width: 80%;
    margin: 0 auto;
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