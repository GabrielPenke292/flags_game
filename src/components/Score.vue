<template>
    <div class="score">
        <div class="score-header">
            <h2 class="score-title">🏆 Score</h2>
        </div>
        <div class="score-container">
            <div class="score-item correct">
                <div class="score-icon">✅</div>
                <div class="score-content">
                    <span class="score-label">Correct</span>
                    <span class="score-value">{{ correctAnswers }}</span>
                </div>
            </div>
            <div class="score-item incorrect">
                <div class="score-icon">❌</div>
                <div class="score-content">
                    <span class="score-label">Incorrect</span>
                    <span class="score-value">{{ incorrectAnswers }}</span>
                </div>
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
    padding: 0;
    border-radius: 20px;
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
    margin: 20px auto;
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(20px);
    border: 1px solid rgba(255, 255, 255, 0.2);
    overflow: hidden;
    transition: all 0.3s ease;
}

.score:hover {
    transform: translateY(-2px);
    box-shadow: 0 12px 40px 0 rgba(31, 38, 135, 0.45);
}

.score-header {
    background: linear-gradient(135deg, rgba(255, 255, 255, 0.2) 0%, rgba(255, 255, 255, 0.1) 100%);
    padding: 20px 25px 15px 25px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    width: 100%;
    text-align: center;
}

.score-title {
    margin: 0;
    color: #fff;
    font-size: 1.3em;
    font-weight: 700;
    background: linear-gradient(135deg, #ffffff 0%, #f3f4f6 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}

.score-container {
    display: flex;
    gap: 30px;
    align-items: center;
    justify-content: center;
    padding: 20px 25px 25px 25px;
    width: 100%;
}

.score-item {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
    padding: 15px 20px;
    border-radius: 12px;
    min-width: 120px;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
}

.score-item::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    opacity: 0.1;
    transition: opacity 0.3s ease;
}

.score-item.correct {
    background: rgba(34, 197, 94, 0.2);
    border: 1px solid rgba(34, 197, 94, 0.3);
}

.score-item.correct::before {
    background: linear-gradient(135deg, #22c55e 0%, #16a34a 100%);
}

.score-item.incorrect {
    background: rgba(239, 68, 68, 0.2);
    border: 1px solid rgba(239, 68, 68, 0.3);
}

.score-item.incorrect::before {
    background: linear-gradient(135deg, #ef4444 0%, #dc2626 100%);
}

.score-item:hover::before {
    opacity: 0.2;
}

.score-icon {
    font-size: 1.2em;
    z-index: 2;
    position: relative;
}

.score-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 4px;
    z-index: 2;
    position: relative;
    text-align: center;
}

.score-label {
    font-size: 0.8em;
    font-weight: 500;
    color: rgba(255, 255, 255, 0.8);
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

.score-value {
    font-size: 1.8em;
    font-weight: 700;
    color: #fff;
    text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
}

.score-item.correct .score-value {
    color: #22c55e;
}

.score-item.incorrect .score-value {
    color: #ef4444;
}

/* Responsive Design */
@media (max-width: 768px) {
    .score {
        padding: 0;
        margin: 15px auto;
    }
    
    .score-header {
        padding: 18px 20px 12px 20px;
    }
    
    .score-title {
        font-size: 1.2em;
    }
    
    .score-container {
        gap: 25px;
        padding: 18px 20px 20px 20px;
    }
    
    .score-item {
        padding: 12px 16px;
        min-width: 100px;
    }
    
    .score-value {
        font-size: 1.6em;
    }
}

@media (max-width: 480px) {
    .score {
        padding: 0;
        margin: 10px auto;
    }
    
    .score-header {
        padding: 15px 18px 10px 18px;
    }
    
    .score-title {
        font-size: 1.1em;
    }
    
    .score-container {
        gap: 20px;
        padding: 15px 18px 18px 18px;
    }
    
    .score-item {
        padding: 10px 14px;
        min-width: 90px;
    }
    
    .score-label {
        font-size: 0.75em;
    }
    
    .score-value {
        font-size: 1.4em;
    }
    
    .score-icon {
        font-size: 1.1em;
    }
}

@media (max-width: 360px) {
    .score-container {
        gap: 15px;
        padding: 12px 15px 15px 15px;
    }
    
    .score-item {
        padding: 8px 12px;
        min-width: 80px;
    }
    
    .score-label {
        font-size: 0.7em;
    }
    
    .score-value {
        font-size: 1.3em;
    }
    
    .score-icon {
        font-size: 1em;
    }
}
</style>