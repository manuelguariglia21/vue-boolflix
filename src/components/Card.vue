<template>
  <div class="card">
    <div
    v-if="cat === 'movie' "
    class="movie-title"
    >
      <h2>{{title}}</h2>
      <p>Titolo originale: {{originalTitle}}</p>
    </div>

    <div
    v-else-if="cat === 'tv' "
    class="tv-title"
    >
      <h2>{{name}}</h2>
      <p>Titolo originale: {{originalName}}</p>
    </div>

    


    <p v-if="language === 'it'">
      Lingua originale: 
      <img src="../assets/img/it.png" :alt="language">
    </p>
    <p v-else-if="language === 'en'">
      Lingua originale: 
      <img src="../assets/img/en.png" :alt="language">
    </p>
    <p v-else>Lingua originale: {{language}}</p>
    <p>Voto: {{vote}}</p>
  </div>
</template>

<script>
export default {
  props:{
    cat: String,

    //General Props
    language: String,
    vote: Number,

    //Movies Props
    title: String,
    originalTitle: String,

    //TV Series Props
    name: String,
    originalName: String,


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
  p{
    img{
      width: 20px;
    }
  }
}

</style>