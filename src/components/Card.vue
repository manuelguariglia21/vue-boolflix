<template>
<div class="flip-card">
  <div class="flip-card-inner">
    <div class="flip-card-front">
      <img src="https://image.tmdb.org/t/p/w300/leE3IJMKd4DoQcmY9NxFKWYZz4w.jpg" alt="Avatar" style="width:300px;height:300px;">
    </div>
    <div class="flip-card-back">
      <div class="movie-title">
        <h2>{{title}}</h2>
        <p>Titolo originale: {{originalTitle}}</p>
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
  </div>
</div>   
</template>

<script>
export default {
  props:{

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

.flip-card {
  background-color: transparent;
  width: 200px;
  height: 300px;
  perspective: 1000px;
  cursor: pointer;
  margin: 10px;
}

.flip-card-inner {
  position: relative;
  width: 200px;
  height: 300px;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 200px;
  height: 300px;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: #bbb;
  color: black;
  overflow: hidden;
}

.flip-card-back {
  background-color: #141414;
    box-shadow: 2px 5px 4px 5px black;
  color: white;
  transform: rotateY(180deg);
  padding: 15px;
  p{
  img{
    width: 20px;
  }
}
}



</style>