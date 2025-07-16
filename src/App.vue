<script setup>
import { ref } from 'vue';
import Swal from 'sweetalert2';
import { flags_and_countries } from './data';
import InstructionsCard from './components/instructionsCard.vue';
import FlagCard from './components/flagCard.vue';
import OptionCard from './components/optionCard.vue';
import Score from './components/Score.vue';

function generateRandomFlagAndOptions(){
  const randomFlag = ref(Object.keys(flags_and_countries)[Math.floor(Math.random() * Object.keys(flags_and_countries).length)]);
  const randomCountry = ref(flags_and_countries[randomFlag.value]);
  // generate 2 more random countries
  const randomCountry2 = ref(flags_and_countries[Object.keys(flags_and_countries)[Math.floor(Math.random() * Object.keys(flags_and_countries).length)]]);
  const randomCountry3 = ref(flags_and_countries[Object.keys(flags_and_countries)[Math.floor(Math.random() * Object.keys(flags_and_countries).length)]]);
  // mix the options
  const options = ref([randomCountry.value, randomCountry2.value, randomCountry3.value]);
  options.value = options.value.sort(() => Math.random() - 0.5);
  return { randomFlag, randomCountry, options };
}

const { randomFlag, randomCountry, options } = generateRandomFlagAndOptions();

// reference to the score component
const scoreRef = ref(null);

function checkAnswer(countryName){
  if(countryName === randomCountry.value){
    // sweet alert 
    Swal.fire({
      title: 'Correct',
      text: 'Your answer is correct!',
      icon: 'success',
      confirmButtonText: 'OK'
    }).then(() => {
      // generate new flag and options
      const newFlag = Object.keys(flags_and_countries)[Math.floor(Math.random() * Object.keys(flags_and_countries).length)];
      const newCountry = flags_and_countries[newFlag];
      
      // generate 2 more random countries
      const newCountry2 = flags_and_countries[Object.keys(flags_and_countries)[Math.floor(Math.random() * Object.keys(flags_and_countries).length)]];
      const newCountry3 = flags_and_countries[Object.keys(flags_and_countries)[Math.floor(Math.random() * Object.keys(flags_and_countries).length)]];
      
      // mix the options
      const newOptions = [newCountry, newCountry2, newCountry3].sort(() => Math.random() - 0.5);
      
      // update the reactive variables
      randomFlag.value = newFlag;
      randomCountry.value = newCountry;
      options.value = newOptions;

      // Incrementar acerto no placar
      scoreRef.value?.correctAnswer();
    });
  }else{
    Swal.fire({
      title: 'Incorrect',
      text: 'Your answer is incorrect!',
      icon: 'error',
      confirmButtonText: 'OK'
    }).then(() => {
      // Incrementar erro no placar
      scoreRef.value?.incorrectAnswer();
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
      <hr class="divider">
      <Score ref="scoreRef" />
    </div>
  </div>
</template>

<style scoped>
header {
  text-align: center;
  font-size: 2.5rem;
  font-weight: bold;
  color: #fff;
  margin: 20px 0;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

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
  flex-wrap: wrap;
}

.divider {
  width: 100%;
  height: 1px;
  background-color: #fff;
  margin: 20px 0;
}

/* Responsive Design */
@media (max-width: 768px) {
  header {
    font-size: 2rem;
    margin: 15px 0;
  }
  
  .container {
    padding: 0 15px;
  }
  
  .option-container {
    gap: 15px;
    flex-direction: column;
  }
}

@media (max-width: 480px) {
  header {
    font-size: 1.5rem;
    margin: 10px 0;
  }
  
  .container {
    padding: 0 10px;
  }
  
  .game-area {
    gap: 15px;
  }
  
  .option-container {
    gap: 10px;
  }
}
</style>
