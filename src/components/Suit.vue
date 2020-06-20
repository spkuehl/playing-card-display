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
  props: {
    suit: String,
    ranks: Array
  }
}
</script>

<style lang="css" scoped>
</style>
