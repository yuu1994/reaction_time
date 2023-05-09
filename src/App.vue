<template>
  <h1>Catch Me If u Can ...</h1>
  <button @click="start" :disabled="isPlaying">Click</button>
  <br>
  <Result :score="score" v-if="end" />
  <div class="" v-if="isPlaying">
    <Block :delay="delay" @endGame="endGame"/>
  </div>
</template>

<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'
export default {
  data(){
    return {
      isPlaying : false,
      delay : null,
      score : 0 ,
      end : false
    }
  },

  components : {
    Block,Result
  },

  methods : {
    start(){
      this.isPlaying = true
      this.delay = Math.floor(2000+Math.random()*5000)
    },
    endGame(score){
      this.score = score
      this.end = true
      this.isPlaying = false
    }
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
