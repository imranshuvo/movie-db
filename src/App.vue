<template>
  <!-- Header -->
  <header-elm></header-elm>

  <!-- Footer -->
  <footer-elm></footer-elm>
</template>

<script>

  import HeaderElm from './components/HeaderElm.vue';
  import FooterElm from './components/FooterElm.vue';

export default {
  name: 'App',
  components: {
    HeaderElm,
    FooterElm
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
* {
  margin: 0;
  padding: 0;
  
}
</style>
