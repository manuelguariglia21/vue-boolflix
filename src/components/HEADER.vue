<template>
  <header>
    <img src="../assets/img/logo.png" alt="">

    <div class="search-box" @keyup.enter="searching">

      <div class="search-bar">

        <select class="form-select form-select-lg mb-3" aria-label=".form-select-lg example" v-model="cat">
          <option value="all">All</option>
          <option value="movie">Movies</option>
          <option value="tv">TV Series</option>
        </select>

        <input v-model="searchedWord" type="text" placeholder="Cerca un titolo...">

        <button class="btn btn-primary" type="submit" @click="searching">Cerca</button>

      </div>
    </div>

  </header>
</template>

<script>
export default {
  data() {
    return{
      searchedWord: ' ',
      cat: ' ',
    }
  },

  methods:{
    searching(){

      console.log('Parola ricercata inviata a App ==> ', this.searchedWord);
      this.$emit('newSearchMovies', this.searchedWord);
      this.$emit('newSearchTv', this.searchedWord);
      this.$emit('selectCat', this.cat);
      console.log(this.cat);
    },
  }
}
</script>

<style lang="scss" scoped>
@import '~bootstrap/scss/bootstrap.scss';
@import url('../assets/style/generals.scss');
@import url('../assets/style/vars.scss');
header{
  width: 100%;
  height: 90px;
  padding: 25px;
  background-color: #141414;
  display: flex;
  align-items: center;
  justify-content: space-between;
  img{
    width: 200px;
  }
  .search-box{
    display: flex;
    justify-content: space-between;
    align-items: center;


    .select-div select {
      -webkit-appearance: none;
      -moz-appearance: none;
      appearance: none;
      
      display: block;
      width: 100%;
      max-width: 320px;
      height: 50px;
      float: right;
      margin: 5px 0px;
      padding: 0px 24px;
      font-size: 16px;
      line-height: 1.75;
      color: black;
      background-color: white;
      background-image: none;
      border: 1px solid #D91921;
      -ms-word-break: normal;
      word-break: normal;
    }


    .search-bar{
      display: flex;
      align-items: top;
      input, button, select{
        padding: 5px;
        font-size: 25px;
        height: 50px;
        border-radius: 0;
      }
      input, select{
        border-top: 3px solid #D91921;
        border-bottom: 3px solid #D91921;
        width: 350px;
      }
      select{ 
        border-left: 3px solid #D91921;
      }
      button{
        border-left: transparent;
        border: 2px solid #D91921;
        background-color: #D91921;
      }
    }
  }
}
</style>