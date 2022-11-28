<template>
  <div id="app">
   <SuperTop />
   <MainBackground  />
  </div>
</template>

<script>
import SuperTop from "./components/header/SuperTop.vue";
import MainBackground from "./components/main/MainBackground.vue";




export default {
  name: 'App',
  components: {
    SuperTop,MainBackground,
  },
  
}
</script>

<style lang="scss">
* {
  margin:0;
  padding:0;
  box-sizing: border-box;
  
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
 
}
</style>


