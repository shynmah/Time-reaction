<template>
  <div class="block" v-if="showBlock" @click="stopTime">click me</div>
</template>

<script>
export default {
    props :['delay'],
    data(){
      return{
        showBlock:false,
        reactiontime : 0,
        timer : null
      }
    },
    mounted(){
      console.log('component mounted');
      setTimeout(() =>{
        this.showBlock=true
        this.startTime()
      }, this.delay)
    },
    methods : {
      startTime(){
        this.timer= setInterval(()=>{
          this.reactiontime += 10
        },10)
      }
      ,
      stopTime(){
        clearInterval(this.timer)
        console.log(this.reactiontime);
      }
    }
}
</script>

<style>
 .block{
    width: 400px;
    border-radius: 22px;
    background-color: #054233;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
    cursor: pointer;
 }

</style>