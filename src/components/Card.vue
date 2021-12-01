<template>
  <div class="card">
    <p>{{title}}</p>
  </div>
</template>

<script>
export default {
  props:{
    title: String,
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