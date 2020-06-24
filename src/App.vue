<template>
  <div id="app">
    <p>Show Top: <input type="number" name="upper" max="13" min="1" v-model="upper" placeholder="13">
      <button type="button" @click="upper--" :disabled="disableDownButton">Show Less</button>
      <button type="button" @click="upper++" :disabled="disableUpButton">Show More</button>
    </p>
    <button type="button" name="all spades" @click="showAllSpades" >Show All Spades</button>
    <br>
    <button type="button" name="reset" @click="resetCards">Reset Round</button>
    <button type="button" name="mobileCards" @click="mobileCards">Change Card Size</button>
    <Suit ref="spades" suit="spades" :ranks="spadesRanks"></Suit>
    <Suit ref="hearts" suit="hearts" :ranks="heartsRanks"></Suit>
    <Suit ref="clubs" suit="clubs" :ranks="clubsRanks"></Suit>
    <Suit ref="diams" suit="diams" :ranks="diamsRanks"></Suit>
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
      spadesRanks: ['A','K','Q','J','10','9','8','7','6','5','4','3','2'],
      heartsRanks: ['A','K','Q','J','10','9','8','7','6','5','4','3','2'],
      clubsRanks: ['A','K','Q','J','10','9','8','7','6','5','4','3','2'],
      diamsRanks: ['A','K','Q','J','10','9','8','7','6','5','4','3','2'],
      ranksList: ['A','K','Q','J','10','9','8','7','6','5','4','3','2'],
      ranks: ['A','K','Q','J','10','9','8','7','6','5','4','3','2'],
      upper: '13',
      disabled: false
    };
  },
  methods: {
    resetCards () {
      this.$refs.spades.$refs.card.forEach(i => i.isActive=true);
      this.$refs.hearts.$refs.card.forEach(i => i.isActive=true);
      this.$refs.clubs.$refs.card.forEach(i => i.isActive=true);
      this.$refs.diams.$refs.card.forEach(i => i.isActive=true);
    },
    showAllSpades () {
      this.spadesRanks = this.ranksList
    },
    mobileCards () {
      this.$refs.spades.$refs.card.forEach(i => i.toggleMobile());
      this.$refs.hearts.$refs.card.forEach(i => i.toggleMobile());
      this.$refs.clubs.$refs.card.forEach(i => i.toggleMobile());
      this.$refs.diams.$refs.card.forEach(i => i.toggleMobile());
    }
  },
  watch: {
    upper: function () {
      this.spadesRanks = (this.ranksList.slice(0,this.upper))
      this.heartsRanks = (this.ranksList.slice(0,this.upper))
      this.clubsRanks = (this.ranksList.slice(0,this.upper))
      this.diamsRanks = (this.ranksList.slice(0,this.upper))
    }
  },
  computed: {
    disableUpButton: function () {
      if (Number(this.upper) <= 12) {
        return false;
      }
      else return true;
    },
    disableDownButton: function () {
      if (Number(this.upper) >= 2) {
        return false;
      }
      else return true;
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
  margin-top: 30px;
}
@import './assets/css/playing-cards/cards.css';
</style>
