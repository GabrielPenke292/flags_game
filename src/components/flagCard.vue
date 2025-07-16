<template>
    <div class="flag-card">
        <div class="flag-container">
            <img :src="`https://flagcdn.com/256x192/${flag}.png`" width="144" height="108" :alt="countryName">
        </div>
        <div class="flag-overlay">
            <div class="country-name">{{ countryName }}</div>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    flag:String,
    countryName:String,
})
</script>

<style scoped>
.flag-card {
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(20px);
    border: 1px solid rgba(255, 255, 255, 0.2);
    color: #fff;
    width: 320px;
    height: 220px;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    font-size: 1.5em;
    font-weight: bold;
    border-radius: 20px;
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
    position: relative;
    overflow: hidden;
    transition: all 0.3s ease;
}

.flag-card:hover {
    transform: translateY(-4px) scale(1.02);
    box-shadow: 0 16px 48px 0 rgba(31, 38, 135, 0.45);
}

.flag-container {
    position: relative;
    z-index: 2;
    padding: 20px;
    border-radius: 15px;
    background: rgba(255, 255, 255, 0.05);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.1);
}

.flag-card img {
    max-width: 100%;
    max-height: 100%;
    object-fit: contain;
    border-radius: 10px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
    transition: all 0.3s ease;
}

.flag-card:hover img {
    transform: scale(1.05);
}

.flag-overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: linear-gradient(135deg, rgba(0, 0, 0, 0.8) 0%, rgba(0, 0, 0, 0.6) 100%);
    padding: 15px;
    transform: translateY(100%);
    transition: transform 0.3s ease;
}

.flag-card:hover .flag-overlay {
    transform: translateY(0);
}

.country-name {
    font-size: 0.8em;
    font-weight: 600;
    color: #fff;
    text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
}

/* Responsive Design */
@media (max-width: 768px) {
    .flag-card {
        width: 300px;
        height: 200px;
    }
    
    .flag-container {
        padding: 15px;
    }
}

@media (max-width: 480px) {
    .flag-card {
        width: 280px;
        height: 180px;
    }
    
    .flag-container {
        padding: 12px;
    }
    
    .flag-overlay {
        padding: 12px;
    }
    
    .country-name {
        font-size: 0.75em;
    }
}

@media (max-width: 360px) {
    .flag-card {
        width: 250px;
        height: 160px;
    }
    
    .flag-container {
        padding: 10px;
    }
    
    .flag-overlay {
        padding: 10px;
    }
    
    .country-name {
        font-size: 0.7em;
    }
}
</style>