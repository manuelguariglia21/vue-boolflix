<template>
  <div id="app">
    <HEADER />
  </div>
</template>

<script>

import HEADER from './components/HEADER.vue';
export default {
  name: 'App',
  components: {
    HEADER
  }
}
</script>

<style lang="scss">
#app {
  @import url('./assets/style/generals.scss');
}
</style>
