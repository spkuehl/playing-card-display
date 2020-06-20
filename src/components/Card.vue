<template>
  <div v-on:click="toggleCard" v-bind:class="{inactive: isActive}" class="playingCards">
    <a class="card" :class="[rankClass, suit]">
      <span class="rank">{{ rank }}</span>
      <span class="suit"><span v-html="suitSymbol"></span></span>
    </a>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    rank: String,
    suit: String
  },
  data: function () {
    return {
      isActive: false
    };
  },
  computed: {
    suitSymbol: function () {
      return "&" + this.suit + ";";
    },
    rankClass: function () {
      return "rank-" + this.rank.toLowerCase();
    }
  },
  methods: {
    toggleCard: function (){
      this.isActive = !this.isActive;
    }
  }
}
</script>

<style lang="css" scoped>
  .playingCards {
    width: 13%;
  }
  .inactive {
    opacity: 25%;
  }
</style>
