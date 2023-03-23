<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Swiper />
  </div>
</template>

<script>
  import Swiper from './components/MySwiper.vue';
  export default {
    name: 'App',
    components: {
      Swiper,

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
</style>