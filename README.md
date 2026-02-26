# loveyou
something special
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para mi persona favorita</title>
    <style>
        body {
            margin: 0;
            overflow-x: hidden;
            background: #ffe5ec;
            font-family: 'Arial', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
        }
        .content {
            z-index: 10;
            background: rgba(255, 255, 255, 0.8);
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            max-width: 80%;
        }
        h1 { color: #ff4d6d; font-size: 2rem; }
        p { color: #590d22; font-size: 1.1rem; }
        
        /* Estilos de la lluvia */
        .heart-rain {
            position: fixed;
            top: -10%;
            user-select: none;
            z-index: 1;
            animation: fall linear forwards;
        }
        @keyframes fall {
            to { transform: translateY(110vh); }
        }
    </style>
</head>
<body>

    <div class="content">
        <h1>❤️ Para [Su Nombre] ❤️</h1>
        <p>Dicen que las mejores cosas de la vida no se planean... simplemente pasan, como tú en mi vida.</p>
        <p>¡Eres increíble!</p>
    </div>

    <script>
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart-rain');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 3 + 2 + 's';
            heart.style.fontSize = Math.random() * 20 + 10 + 'px';
            heart.style.opacity = Math.random();
            
            document.body.appendChild(heart);
            
            setTimeout(() => {
                heart.remove();
            }, 5000);
        }
        setInterval(createHeart, 300);
    </script>
</body>
</html>
