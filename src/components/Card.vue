<template>
  <div class="playing-card">
    <p>{{rank}}</p>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    rank: String
  }
}
</script>

<style lang="css" scoped>
  .playing-card {
    background-color: blue;
    width: 13%;
    height: 25%;
  }
</style>
