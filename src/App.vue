<template>
  <div id="app">
    <!--<img src="./assets/logo.png">-->
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
html{
  width: 100%;
  height: 100%;
  box-sizing: border-box;
  /*border: 3px solid #ff00ff;*/
  /*padding: 3px;*/
}
 body{
   width: 100%;
   height: 100%;
   position: relative;
   box-sizing: border-box;
   /*border: 3px solid #00ff00;*/
   /*padding: 3px;*/
   -webkit-touch-callout: none;
   -webkit-user-select: none;
 }
  div, header, footer, ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }
</style>
