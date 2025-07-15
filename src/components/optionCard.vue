<template>
    <div class="option-card">
        <p>{{ option }}</p>
    </div>
</template>

<script setup>

const props = defineProps({
    option:String,
})

</script>

<style scoped>
.option-card {
    background-color: oklch(80.9% 0.105 251.813);
    color: #fff;
    padding: 15px 25px;
    border-radius: 10px;
    width: 120px;
    height: 60px;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    font-size: 1.2em;
    font-weight: bold;
    cursor: pointer;
    transition: transform 0.2s ease;
}

.option-card:hover {
    transform: scale(1.05);
}
</style>