<template>
  <div id="app">
    upper: <input type="number" name="upper" max="14" min="1" v-model="upper" placeholder="14">
    <Suit suit="spades" :ranks="ranks"></Suit>
    <Suit suit="hearts" :ranks="ranks"></Suit>
    <Suit suit="clubs" :ranks="ranks"></Suit>
    <Suit suit="diams" :ranks="ranks"></Suit>
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
      ranksList: ['A','K','Q','J','10','9','8','7','6','5','4','3','2'],
      ranks: ['A','K','Q','J','10','9','8','7','6','5','4','3','2'],
      upper: '14',
    };
  },
  watch: {
    upper: function () {
      this.ranks = (this.ranksList.slice(0,this.upper))
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
