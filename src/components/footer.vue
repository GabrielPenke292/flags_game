<template>
    <footer>
        <div class="footer-content">
            <p>Developed with ❤️ by <a href="https://www.linkedin.com/in/gabriel-penke-953771206/" target="_blank">Gabriel Penke</a></p>
        </div>
    </footer>
</template>

<style scoped>
footer {
    text-align: center;
    color: #fff;
    padding: 25px;
    margin-top: auto;
    background: rgba(255, 255, 255, 0.05);
    backdrop-filter: blur(20px);
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    position: relative;
    overflow: hidden;
}

footer::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent 0%, rgba(255, 255, 255, 0.3) 50%, transparent 100%);
}

.footer-content {
    position: relative;
    z-index: 2;
}

footer p {
    margin: 0;
    font-size: 0.95em;
    opacity: 0.9;
    font-weight: 500;
    letter-spacing: 0.5px;
}

footer a {
    color: #60a5fa;
    text-decoration: none;
    font-weight: 600;
    transition: all 0.3s ease;
    position: relative;
}

footer a::after {
    content: '';
    position: absolute;
    bottom: -2px;
    left: 0;
    width: 0;
    height: 2px;
    background: linear-gradient(90deg, #60a5fa 0%, #3b82f6 100%);
    transition: width 0.3s ease;
}

footer a:hover {
    color: #3b82f6;
    text-shadow: 0 0 8px rgba(96, 165, 250, 0.5);
}

footer a:hover::after {
    width: 100%;
}

/* Responsive Design */
@media (max-width: 768px) {
    footer {
        padding: 20px;
    }
    
    footer p {
        font-size: 0.9em;
    }
}

@media (max-width: 480px) {
    footer {
        padding: 18px;
    }
    
    footer p {
        font-size: 0.85em;
    }
}
</style>