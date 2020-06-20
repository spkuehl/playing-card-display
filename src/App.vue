<template>
  <div id="app">
    <Suit suit="spades"></Suit>
    <Suit suit="hearts"></Suit>
    <Suit suit="clubs"></Suit>
    <Suit suit="diams"></Suit>
  </div>
</template>

<script>
import Suit from './components/Suit.vue'

export default {
  name: 'App',
  components: {
    Suit
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
