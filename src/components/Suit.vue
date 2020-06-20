<template>
  <div class="playingCards">
    <ul class="table">
      <li  v-for="rank in ranks" v-bind:key="rank">
        <Card v-bind:key="rank" v-bind:rank="rank" v-bind:suit="suit"></Card>
      </li>
    </ul>
  </div>
</template>

<script>
import Card from './Card.vue'
export default {
  components: {
    Card
  },
  data: function () {
    return {
      ranks: ['A','K','Q','J','10','9','8','7','6','5','4','3','2']
    };
  },
  props: {
    suit: String
  }
}
</script>

<style lang="css" scoped>
</style>
