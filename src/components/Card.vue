<template>
  <div v-on:click="toggleCard" class="playingCards faceImages">
    <a class="card"
       :class="[rankClass, [(isActive) ? suit : ''], {back: !isActive}]"
       v-bind:style='{"font-size": (isMobile ? ".6em" : "1.2em"),
                      "background-position": (isMobile ? "-35px 0" : "0 0")}' >
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
      isActive: true,
      isMobile: false
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
    },
    toggleMobile: function () {
      this.isMobile = !this.isMobile;
    }
  }
}
</script>

<style lang="css" scoped>

</style>
