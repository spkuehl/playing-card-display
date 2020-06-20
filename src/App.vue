<template>
  <div id="app">
    <button v-on:click="toggleFaceOnly">Face Cards Only</button>
    <Suit suit="spades" :ranks="ranks" faceOnly=faceOnly></Suit>
    <Suit suit="hearts" :ranks="ranks" faceOnly=faceOnly></Suit>
    <Suit suit="clubs" :ranks="ranks" faceOnly=faceOnly></Suit>
    <Suit suit="diams" :ranks="ranks" faceOnly=faceOnly></Suit>
  </div>
</template>

<script>
import Suit from './components/Suit.vue'

export default {
  name: 'App',
  components: {
    Suit
  },
  data: function () {
    return {
      faceOnly: false,
      ranks: ['A','K','Q','J','10','9','8','7','6','5','4','3','2']
    };
  },
  methods: {
    toggleFaceOnly: function (){
      this.faceOnly = !this.faceOnly;
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
@import './assets/css/playing-cards/cards.css';
</style>
