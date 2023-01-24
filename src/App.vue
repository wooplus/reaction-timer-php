<template>
  <h1>How fast can you catch me?</h1>
  <button @click="play" :disabled="isPlaying">play</button>
  <div v-if="isPlaying">
    <Block :delay="delay" @endGame="endGame"/>
  </div>
  <div v-if="showResult">
    <Result :score="score"></Result>
  </div>
</template>

<script>

import Result from './components/Result'
import Block from './components/Block'
export default {
  name: 'App',
  components: {
    Result,
    Block,
  },
  data() {
    return {
      isPlaying:false,
      delay:null,
      score:0,
      showResult:false
    }
  },
  methods:{
    play() {
      this.isPlaying = true
      this.delay = 2000+Math.random()*3000;
      this.showResult = false
    },
    endGame(score) {
      this.score= score;
      this.isPlaying= false;
      this.showResult = true;
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
