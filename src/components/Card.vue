<template>
  <div class="card">
    <h2>{{title}}</h2>
    <p>Titolo originale: {{originalTitle}}</p>
    <p>Lingua: {{language}}</p>
    <p>Voto: {{vote}}</p>
  </div>
</template>

<script>
export default {
  props:{
    title: String,
    originalTitle: String,
    language: String,
    vote: String
    
  }
}
</script>

<style lang="scss" scoped>

.card{
  width: 200px;
  min-height: 300px;
  background-color: white;
  border-radius: 30px;
  margin: 5px;
  color: black;
  text-align: center;
  padding: 10px;
}

</style>