<template>
  <div id="app">
    <!-- <UserComment/> -->
    <ToDo/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import UserComment from './components/comment/UserComment'
import ToDo from './components/todo/ToDo'

export default {
  name: 'App',
  components: {
    HelloWorld,
    UserComment,
    ToDo
  }
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
