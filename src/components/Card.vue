<template>
  <div v-on:click="toggleCard" v-bind:class="{active: isActive}" class="playing-card">
    <p>{{rank}}</p>
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
      isActive: true
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
  .playing-card {
    width: 13%;
    border-style: groove;
    height: 125px;
  }
  .active {
    color: blue;
  }
</style>
