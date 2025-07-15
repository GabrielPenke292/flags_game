<script setup>
import { ref } from 'vue';
import InstructionsCard from './components/instructionsCard.vue';
import FlagCard from './components/flagCard.vue';
</script>

<template>
  <header>Flag's Game</header>
  <div class="container">
    <InstructionsCard />
    <FlagCard />
  </div>
</template>

<style scoped>

</style>
