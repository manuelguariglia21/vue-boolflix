<template>
  <header>
    <img src="../assets/img/logo.png" alt="">
    <div class="serach-bar">
      <input type="text" placeholder="Cerca un titolo...">
    </div>
  </header>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import url('../assets/style/generals.scss');
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
  input[type=text] {
  border: 3px solid red;
  padding: 5px;
  height: 50px;
  width: 350px;
  border-radius: 4px;
  font-size: 25px;
  }
}
</style>