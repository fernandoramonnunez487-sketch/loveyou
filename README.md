# Te amo Guada

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
        <h1>❤️ te extraño ❤️</h1>
        <p>hoy te extrañé más que ayer, se volvió mi hábito aunque sé que algún día voy a sanar hoy prefiero disfrutar el pálpito de mi corazón al soñar con tu hermosa alma y no quiero olvidar todos tus besos cuáles hacen de mis huesos olvidar que soy un humano más pues son los mismos que me hacen volar y al recapacitar de este sueño me refuta que es real el amor que siento</p>
        <p>mi diosa mi todo</p>
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
