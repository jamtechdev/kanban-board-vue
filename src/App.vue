<template>
  <div id="app">
    <Board/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import Board from './components/Board.vue';
import './style/main.scss'
export default Vue.extend({
  name: 'App',
  components: {
    Board
  }
});
</script>

<style lang="scss">

  
</style>
