<template>
    <div class="option-card" @click="optionSelected">
        <p>{{ option }}) {{ countryName }}</p>
    </div>
</template>

<script setup>
import { defineEmits } from 'vue';

const emit = defineEmits(['optionSelected']);

function optionSelected(){
    emit('optionSelected', props.countryName);
}

const props = defineProps({
    option:String,
    countryName:String,
})
</script>

<style scoped>
.option-card {
    background-color: oklch(80.9% 0.105 251.813);
    color: #fff;
    padding: 15px 25px;
    border-radius: 10px;
    width: 150px;
    height: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    font-size: 1.2em;
    font-weight: bold;
    cursor: pointer;
    transition: transform 0.2s ease;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.option-card:hover {
    transform: scale(1.05);
}

.option-card p {
    margin: 0;
    line-height: 1.3;
    word-wrap: break-word;
}

/* Responsive Design */
@media (max-width: 768px) {
    .option-card {
        width: 140px;
        height: 90px;
        padding: 12px 20px;
        font-size: 1.1em;
    }
}

@media (max-width: 480px) {
    .option-card {
        width: 120px;
        height: 80px;
        padding: 10px 15px;
        font-size: 1em;
    }
}

@media (max-width: 360px) {
    .option-card {
        width: 100px;
        height: 70px;
        padding: 8px 12px;
        font-size: 0.9em;
    }
}
</style>