<template>
    <footer>
        <p>Developed by <a href="https://www.linkedin.com/in/gabriel-penke-953771206/" target="_blank">Gabriel Penke</a></p>
    </footer>
</template>

<style scoped>
footer {
    text-align: center;
    color: #fff;
    padding: 20px;
    margin-top: auto;
    background-color: rgba(255, 255, 255, 0.05);
    border-top: 1px solid rgba(255, 255, 255, 0.1);
}

footer p {
    margin: 0;
    font-size: 0.9em;
    opacity: 0.8;
}

footer a {
    color: #646cff;
    text-decoration: none;
    font-weight: 500;
    transition: color 0.3s ease;
}

footer a:hover {
    color: #535bf2;
    text-decoration: underline;
}

/* Responsive Design */
@media (max-width: 768px) {
    footer {
        padding: 15px;
    }
    
    footer p {
        font-size: 0.85em;
    }
}

@media (max-width: 480px) {
    footer {
        padding: 12px;
    }
    
    footer p {
        font-size: 0.8em;
    }
}
</style>