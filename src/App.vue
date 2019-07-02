<template>
  <div id="app">
    <img class="profilePic" alt="Vue logo" src="./assets/donut.png">
    <HelloWorld msg="Welcome to Ana's world!!!"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
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

.profilePic {
  width: 20%;
}
</style>
