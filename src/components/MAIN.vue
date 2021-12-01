<template>
  <main>
    <div class="card-box">
      
    </div>
  </main>
</template>

<script>
export default {

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
    justify-content: start;
    align-items: center;
    color: white;
  }
}

</style>