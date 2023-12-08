<template>
  <h1>Catch Me If You Can!</h1>
  <button class="play" v-on:click="startGame()">play</button>
  <div v-if="isPlaying">
    <Block :delay="delay" @endGame="endGame"></Block>
  </div>
  <div v-if="end">
    <Result :score="score"></Result>
  </div>
</template>

<script>

import Block from "./components/Block.vue"
import Result from "./components/Result.vue"
export default {
  name: 'App',
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: 0,
      end: false,
    }
  },
  components: {
    Block,
    Result
  },
  methods: {
    startGame() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 4000;
      this.end= false
    },
    endGame(score) {
      this.score = score;
      this.isPlaying = false;
      this.end = true;
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
  color: #2c3e50;
  margin-top: 60px;
}
.play{
  padding: 10px 20px;
  background-color: rgb(52, 131, 215);
  color: white;
  border: none;
  cursor: pointer;
}

</style>
