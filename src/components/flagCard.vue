<template>
    <div class="flag-card">
        <img :src="`https://flagcdn.com/256x192/${flag}.png`" width="144" height="108" :alt="countryName">
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
    background-color: oklch(80.9% 0.105 251.813);
    color: #fff;
    width: 300px;
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    font-size: 1.5em;
    font-weight: bold;
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.flag-card img {
    max-width: 100%;
    max-height: 100%;
    object-fit: contain;
    border-radius: 5px;
}

/* Responsive Design */
@media (max-width: 768px) {
    .flag-card {
        width: 280px;
        height: 180px;
    }
}

@media (max-width: 480px) {
    .flag-card {
        width: 250px;
        height: 160px;
    }
}

@media (max-width: 360px) {
    .flag-card {
        width: 220px;
        height: 140px;
    }
}
</style>