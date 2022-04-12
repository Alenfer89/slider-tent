<template>
  <div id="app">
    <Portfolio />
  </div>
</template>

<script>
import Portfolio from './components/SectionPortfolio.vue';

export default {
  name: 'App',
  components: {
    Portfolio
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  //max-width: 100vw;
}
</style>
