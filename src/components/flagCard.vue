<template>
    <div class="flag-card">
        <img src="../assets/flags/flag.png" alt="flag" />
    </div>
</template>

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
}

.flag-card img {
    max-width: 100%;
    max-height: 100%;
    object-fit: contain;
}
</style>