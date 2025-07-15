<script setup>
import { ref } from 'vue';
import InstructionsCard from './components/instructionsCard.vue';
import FlagCard from './components/flagCard.vue';
import OptionCard from './components/optionCard.vue';
</script>

<template>
  <header>Flag's Game</header>
  <div class="container">
    <InstructionsCard />
    <div class="game-area">
      <FlagCard flag="au" countryName="Australia" />
      <div class="option-container">
        <OptionCard option="A" countryName="Brazil" />
        <OptionCard option="B" countryName="Argentina" />
        <OptionCard option="C" countryName="Chile" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.game-area {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  gap: 20px;
}

.option-container {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
  width: 100%;
}
</style>
