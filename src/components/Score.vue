<template>
    <div class="score">
        <h2 class="score-title">Score</h2>
        <div class="score-container">
            <div class="score-item correct">
                <span class="score-label">Acertos:</span>
                <span class="score-value">{{ correctAnswers }}</span>
            </div>
            <div class="score-item incorrect">
                <span class="score-label">Erros:</span>
                <span class="score-value">{{ incorrectAnswers }}</span>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const correctAnswers = ref(0);
const incorrectAnswers = ref(0);

const emit = defineEmits(['correctAnswer', 'incorrectAnswer']);

function correctAnswer(){
    correctAnswers.value++;
    emit('correctAnswer');
}

function incorrectAnswer(){
    incorrectAnswers.value++;
    emit('incorrectAnswer');
}

// Expor as funções para o componente pai
defineExpose({
    correctAnswer,
    incorrectAnswer
});
</script>

<style scoped>
.score {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 100%;
    max-width: 500px;
    padding: 15px;
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    margin: 20px auto;
    background-color: #f8f9fa;
}

.score-title {
    margin: 0 0 15px 0;
    color: #333;
    font-size: 1.2em;
    font-weight: 600;
}

.score-container {
    display: flex;
    gap: 30px;
    align-items: center;
}

.score-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5px;
    padding: 10px 20px;
    border-radius: 8px;
    min-width: 80px;
}

.score-item.correct {
    background-color: #d4edda;
    border: 2px solid #28a745;
}

.score-item.incorrect {
    background-color: #f8d7da;
    border: 2px solid #dc3545;
}

.score-label {
    font-size: 0.9em;
    font-weight: 500;
    color: #495057;
}

.score-value {
    font-size: 1.5em;
    font-weight: bold;
}

.score-item.correct .score-value {
    color: #28a745;
}

.score-item.incorrect .score-value {
    color: #dc3545;
}

/* Responsive Design */
@media (max-width: 768px) {
    .score {
        padding: 12px;
        margin: 15px auto;
    }
    
    .score-title {
        font-size: 1.1em;
        margin: 0 0 12px 0;
    }
    
    .score-container {
        gap: 25px;
    }
    
    .score-item {
        padding: 8px 16px;
        min-width: 70px;
    }
    
    .score-value {
        font-size: 1.3em;
    }
}

@media (max-width: 480px) {
    .score {
        padding: 10px;
        margin: 10px auto;
    }
    
    .score-title {
        font-size: 1em;
        margin: 0 0 10px 0;
    }
    
    .score-container {
        gap: 20px;
    }
    
    .score-item {
        padding: 6px 12px;
        min-width: 60px;
    }
    
    .score-label {
        font-size: 0.8em;
    }
    
    .score-value {
        font-size: 1.2em;
    }
}

@media (max-width: 360px) {
    .score-container {
        gap: 15px;
    }
    
    .score-item {
        padding: 5px 10px;
        min-width: 50px;
    }
    
    .score-label {
        font-size: 0.7em;
    }
    
    .score-value {
        font-size: 1.1em;
    }
}
</style>