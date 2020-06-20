<template>
  <div v-on:click="toggleCard" class="playingCards">
    <a class="card" :class="[rankClass, [(isActive) ? suit : ''], {back: !isActive}]">
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
      isActive: true
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

</style>
