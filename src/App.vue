<template>
  <div id="app">
    <nav class="navbar navbar-light bg-light">
      <a class="navbar-brand" href="">
        <img src='http://localhost:8080/inventarioBack/public/images/icono.jpg' width="30" height="30" alt="">
        REGISTAL UDI
      </a>
      <a class="navbar-brand" href="">
        <img src='http://localhost:8080/inventarioBack/public/images/marca.svg' width="30" height="30" alt="">
        MARCAS
      </a>
      <a class="navbar-brand" href=''>
        <i class="fa fa-building"></i>EDIFICIOS
      </a>
      <a class="navbar-brand" href=''>
        <i class="fa fa-laptop"></i>
        TIPO DE EQUIPOS
      </a>
    </nav>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
