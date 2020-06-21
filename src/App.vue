<template>
  <div id="app">
    <button type="button" name="reset" @click="resetCards" >Reset</button>
    upper: <input type="number" name="upper" max="13" min="1" v-model="upper" placeholder="13">
    <Suit ref="spades" suit="spades" :ranks="ranks"></Suit>
    <Suit ref="hearts" suit="hearts" :ranks="ranks"></Suit>
    <Suit ref="clubs" suit="clubs" :ranks="ranks"></Suit>
    <Suit ref="diams" suit="diams" :ranks="ranks"></Suit>
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
      upper: '13',
    };
  },
  methods: {
    resetCards () {
      this.$refs.spades.$refs.card.forEach(i => i.isActive=true);
      this.$refs.hearts.$refs.card.forEach(i => i.isActive=true);
      this.$refs.clubs.$refs.card.forEach(i => i.isActive=true);
      this.$refs.diams.$refs.card.forEach(i => i.isActive=true);
    }
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
