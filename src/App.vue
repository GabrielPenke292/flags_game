<script setup>
import { ref } from 'vue';
import InstructionsCard from './components/instructionsCard.vue';
import FlagCard from './components/flagCard.vue';
import OptionCard from './components/optionCard.vue';
import { flags_and_countries } from './data';
import Swal from 'sweetalert2';
// generate a random flag and country
const randomFlag = ref(Object.keys(flags_and_countries)[Math.floor(Math.random() * Object.keys(flags_and_countries).length)]);
const randomCountry = ref(flags_and_countries[randomFlag.value]);
// generate 2 more random countries
const randomCountry2 = ref(flags_and_countries[Object.keys(flags_and_countries)[Math.floor(Math.random() * Object.keys(flags_and_countries).length)]]);
const randomCountry3 = ref(flags_and_countries[Object.keys(flags_and_countries)[Math.floor(Math.random() * Object.keys(flags_and_countries).length)]]);
// mix the options
const options = ref([randomCountry.value, randomCountry2.value, randomCountry3.value]);
options.value = options.value.sort(() => Math.random() - 0.5);

function checkAnswer(countryName){
  if(countryName === randomCountry.value){
    // sweet alert 
    Swal.fire({
      title: 'Correct',
      text: 'Your answer is correct!',
      icon: 'success',
      confirmButtonText: 'OK'
    });
  }else{
    Swal.fire({
      title: 'Incorrect',
      text: 'Your answer is incorrect!',
      icon: 'error',
      confirmButtonText: 'OK'
    });
  }
}
</script>

<template>
  <header>Flag's Game</header>
  <div class="container">
    <InstructionsCard />
    <div class="game-area">
      <FlagCard :flag="randomFlag" :countryName="randomCountry" />
      <div class="option-container">
        <OptionCard v-for="(option, index) in options" :key="index" :option="index + 1" :countryName="option" @optionSelected="checkAnswer" /> 
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
