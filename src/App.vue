<script setup>
import { ref } from 'vue';
import InstructionsCard from './components/instructionsCard.vue';
import FlagCard from './components/flagCard.vue';
import OptionCard from './components/optionCard.vue';
import { flags_and_countries } from './data';
// generate a random flag and country
const randomFlag = ref(Object.keys(flags_and_countries)[Math.floor(Math.random() * Object.keys(flags_and_countries).length)]);
const randomCountry = ref(flags_and_countries[randomFlag.value]);
</script>

<template>
  <header>Flag's Game</header>
  <div class="container">
    <InstructionsCard />
    <div class="game-area">
      <FlagCard :flag="randomFlag" :countryName="randomCountry" />
      <div class="option-container">
        <OptionCard option="A" :countryName="randomCountry" />
        <OptionCard option="B" :countryName="randomCountry" />
        <OptionCard option="C" :countryName="randomCountry" />
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
