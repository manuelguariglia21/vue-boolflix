<template>
  <header>
    <img src="../assets/img/logo.png" alt="">

    <div class="search-box" @keyup.enter="searching">
      <div class="select-div">
        <label>
            <select v-model="cat">
                <option selected>all</option>
                <option>movie</option>
                <option>tv</option>
            </select>
        </label>
      </div>

    <div class="search-bar">
      <input v-model="searchedWord" type="text" placeholder="Cerca un titolo...">
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
      this.$emit('newSearchMovies', this.searchedWord, this.cat);
      this.$emit('newSearchTv', this.searchedWord, this.cat);
    },
  }
}
</script>

<style lang="scss" scoped>
@import url('../assets/style/generals.scss');
@import url('../assets/style/vars.scss');
header{
  width: 100%;
  height: 90px;
  padding: 25px;
  background-color: black;
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
      input{
        border: 3px solid #D91921;
        padding: 5px;
        height: 50px;
        width: 350px;
        border-radius: 4px;
        font-size: 25px;
      }
    }
  }
}
</style>