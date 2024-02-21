<template>
  <h1>Reaction Timer</h1>
  <button @click="start " :disabled="isplaying">play</button>
  <!-- <p v-if="showResault">Reaction : {{ score }} ms</p> -->
  <block v-if="isplaying" :delay="delay" @end="endgame"/>
  <results v-if="showResault" :score="score"/>
</template>

<script>
import block from './components/Block.vue'
import results from './components/Results.vue'
export default {
  name: 'App',
  components: {block , results},
  data(){
    return{
      delay: null,
      isplaying : false,
      showResault : false,
      score : null
    }
  },
  methods :{
    start(){
      this.delay= 2000 + Math.random()*5000
      this.isplaying = true
      this.showResault = false
    },
    endgame(reaction){
      this.score=reaction
      this.isplaying = false
      this.showResault = true
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
button {
  background-color: #054233;
  width: 75px;
  height: 30px;
  border-radius: 12px;
  border: none;
  color: azure;
  font-size: 14px;
  cursor: pointer;
}
button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
