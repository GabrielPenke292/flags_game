<template>
    <div class="instructions-card">
        <h2>Instructions</h2>
        <p>You will be given a random country flag and you need to guess the country name.</p>
        <p>Click on the correct option (1, 2 or 3) to guess the country flag displayed.</p>
    </div>
</template>

<style scoped>
.instructions-card {
    background-color: oklch(80.9% 0.105 251.813);
    color: #fff;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.1);
    width: 100%;
    height: fit-content;
    text-align: center;
    font-size: 1.2em;
    font-weight: bold;
    margin: 0;
}

.instructions-card h2 {
    margin: 0 0 15px 0;
    font-size: 1.5em;
}

.instructions-card p {
    margin: 10px 0;
    line-height: 1.4;
}

/* Responsive Design */
@media (max-width: 768px) {
    .instructions-card {
        padding: 15px;
        font-size: 1.1em;
        margin: 0;
    }
    
    .instructions-card h2 {
        font-size: 1.3em;
    }
}

@media (max-width: 480px) {
    .instructions-card {
        padding: 12px;
        font-size: 1em;
        margin: 0;
    }
    
    .instructions-card h2 {
        font-size: 1.2em;
        margin: 0 0 10px 0;
    }
    
    .instructions-card p {
        margin: 8px 0;
        line-height: 1.3;
    }
}
</style>