<template>
  <div id="app">
    <!-- 
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    -->
    <monedas/>
    <masa/>
    <longitud/>
    <tiempo/>
    <almacenamiento/>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import monedas from './components/monedas.vue'
import Masa from './components/Masa.vue'
import longitud from './components/longitud.vue'
import tiempo from "./components/tiempo.vue"
import almacenamiento from "./components/almacenamiento.vue"


export default {
  name: 'App',
  components: {
  //  HelloWorld
  monedas,
  Masa,
  longitud,
  tiempo,  
  almacenamiento,


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
