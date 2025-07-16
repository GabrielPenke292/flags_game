<template>
    <div class="option-card" @click="optionSelected">
        <div class="option-content">
            <div class="option-number">{{ option }}</div>
            <div class="option-text">{{ countryName }}</div>
        </div>
        <div class="option-overlay"></div>
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
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(20px);
    border: 1px solid rgba(255, 255, 255, 0.2);
    color: #fff;
    padding: 0;
    border-radius: 16px;
    width: 160px;
    height: 110px;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    font-size: 1.1em;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    box-shadow: 0 4px 16px 0 rgba(31, 38, 135, 0.3);
    position: relative;
    overflow: hidden;
}

.option-card:hover {
    transform: translateY(-3px) scale(1.05);
    box-shadow: 0 8px 24px 0 rgba(31, 38, 135, 0.4);
    border-color: rgba(255, 255, 255, 0.4);
}

.option-card:active {
    transform: translateY(-1px) scale(1.02);
}

.option-content {
    position: relative;
    z-index: 2;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    padding: 15px;
    width: 100%;
    height: 100%;
    justify-content: center;
}

.option-number {
    background: linear-gradient(135deg, #3b82f6 0%, #1d4ed8 100%);
    color: white;
    width: 28px;
    height: 28px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.9em;
    font-weight: 700;
    box-shadow: 0 2px 8px rgba(59, 130, 246, 0.4);
}

.option-text {
    font-size: 0.85em;
    font-weight: 500;
    line-height: 1.3;
    word-wrap: break-word;
    color: rgba(255, 255, 255, 0.95);
    max-width: 100%;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
}

.option-overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: linear-gradient(135deg, rgba(59, 130, 246, 0.1) 0%, rgba(29, 78, 216, 0.1) 100%);
    opacity: 0;
    transition: opacity 0.3s ease;
}

.option-card:hover .option-overlay {
    opacity: 1;
}

/* Responsive Design */
@media (max-width: 768px) {
    .option-card {
        width: 150px;
        height: 100px;
        font-size: 1em;
    }
    
    .option-content {
        padding: 12px;
        gap: 6px;
    }
    
    .option-number {
        width: 26px;
        height: 26px;
        font-size: 0.85em;
    }
    
    .option-text {
        font-size: 0.8em;
    }
}

@media (max-width: 480px) {
    .option-card {
        width: 130px;
        height: 90px;
        font-size: 0.95em;
    }
    
    .option-content {
        padding: 10px;
        gap: 5px;
    }
    
    .option-number {
        width: 24px;
        height: 24px;
        font-size: 0.8em;
    }
    
    .option-text {
        font-size: 0.75em;
    }
}

@media (max-width: 360px) {
    .option-card {
        width: 110px;
        height: 80px;
        font-size: 0.9em;
    }
    
    .option-content {
        padding: 8px;
        gap: 4px;
    }
    
    .option-number {
        width: 22px;
        height: 22px;
        font-size: 0.75em;
    }
    
    .option-text {
        font-size: 0.7em;
    }
}
</style>