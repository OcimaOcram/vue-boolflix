<template>
  <div id="app">
    <MyFilm/>
    
  </div>
</template>

<script>
import MyFilm from './components/MyFilm.vue';



export default {
  name: 'App',
  components: {
    MyFilm,
    
}
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}
* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
</style>
