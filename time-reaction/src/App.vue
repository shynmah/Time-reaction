<template>
  <h1>Reaction Timer</h1>
  <button @click="start " :disabled="isplaying">play</button>
  <block v-if="isplaying" :delay="delay"/>
</template>

<script>
import block from './components/Block.vue'
export default {
  name: 'App',
  components: {block},
  data(){
    return{
      delay: null,
      isplaying : false
    }
  },
  methods :{
    start(){
      this.delay= 2000 + Math.random()*5000
      this.isplaying = true
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
