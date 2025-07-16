<template>
    <div class="instructions-card">
        <div class="card-header">
            <h2>📋 Instructions</h2>
        </div>
        <div class="card-content">
            <p>You will be given a random country flag and you need to guess the country name.</p>
            <p>Click on the correct option (1, 2 or 3) to guess the country flag displayed.</p>
        </div>
    </div>
</template>

<style scoped>
.instructions-card {
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(20px);
    border: 1px solid rgba(255, 255, 255, 0.2);
    color: #fff;
    padding: 0;
    border-radius: 20px;
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
    width: 100%;
    height: fit-content;
    text-align: left;
    font-size: 1.1em;
    font-weight: 500;
    margin: 0;
    overflow: hidden;
    transition: all 0.3s ease;
}

.instructions-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 12px 40px 0 rgba(31, 38, 135, 0.45);
}

.card-header {
    background: linear-gradient(135deg, rgba(255, 255, 255, 0.2) 0%, rgba(255, 255, 255, 0.1) 100%);
    padding: 20px 25px 15px 25px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.card-header h2 {
    margin: 0;
    font-size: 1.4em;
    font-weight: 700;
    background: linear-gradient(135deg, #ffffff 0%, #f3f4f6 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}

.card-content {
    padding: 20px 25px 25px 25px;
}

.card-content p {
    margin: 12px 0;
    line-height: 1.6;
    color: rgba(255, 255, 255, 0.9);
    font-size: 0.95em;
}

.card-content p:first-child {
    margin-top: 0;
}

.card-content p:last-child {
    margin-bottom: 0;
}

/* Responsive Design */
@media (max-width: 768px) {
    .instructions-card {
        font-size: 1em;
    }
    
    .card-header {
        padding: 18px 20px 12px 20px;
    }
    
    .card-header h2 {
        font-size: 1.3em;
    }
    
    .card-content {
        padding: 18px 20px 20px 20px;
    }
}

@media (max-width: 480px) {
    .instructions-card {
        font-size: 0.95em;
    }
    
    .card-header {
        padding: 15px 18px 10px 18px;
    }
    
    .card-header h2 {
        font-size: 1.2em;
    }
    
    .card-content {
        padding: 15px 18px 18px 18px;
    }
    
    .card-content p {
        margin: 10px 0;
        line-height: 1.5;
        font-size: 0.9em;
    }
}
</style>