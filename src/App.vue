<template>
  <div id="app">
    <HEADER />
    <MAIN />
  </div>
</template>

<script>

import HEADER from './components/HEADER.vue';
import MAIN from './components/MAIN.vue';
export default {
  name: 'App',
  components: {
    HEADER,
    MAIN
  }
}
</script>

<style lang="scss">
#app {
  @import url('./assets/style/generals.scss');
}
</style>
