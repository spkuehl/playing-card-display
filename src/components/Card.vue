<template>
  <div v-on:click="toggleCard" v-bind:class="{inactive: isActive}" class="playingCards">
    <a class="card rank-k spades">
      <span class="rank">K</span>
      <span class="suit">&hearts;</span>
    </a>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    rank: String,
  },
  data: function () {
    return {
      isActive: false
    };
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
    opacity: 50%;
  }
</style>
