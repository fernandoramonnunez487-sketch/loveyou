<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Te amo Guada</title>
    <style>
        /* AJUSTES PARA MÓVIL */
        * { box-sizing: border-box; }
        
        body {
            margin: 0;
            padding: 0;
            background: radial-gradient(circle, #3d0000 0%, #000000 100%);
            font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            color: #ffffff;
            text-align: center;
            overflow: hidden; /* Evita scrolls raros en móvil */
        }

        .container {
            width: 90%;
            max-width: 400px; /* Tamaño ideal de un celular */
            padding: 25px;
            background: rgba(0, 0, 0, 0.6);
            border-radius: 20px;
            border: 1px solid rgba(255, 77, 109, 0.4);
            box-shadow: 0 0 20px rgba(0,0,0,0.5);
        }

        h1 {
            color: #ff4d6d;
            font-size: 1.8rem;
            margin-bottom: 15px;
            text-shadow: 0 0 10px rgba(255, 77, 109, 0.5);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .poema {
            font-size: 1rem;
            line-height: 1.6;
            color: #e0e0e0;
            font-style: italic;
            margin-bottom: 30px;
            word-wrap: break-word;
        }

        /* BOTÓN MÁS GRANDE PARA MÓVIL */
        .music-btn {
            background-color: #ff4d6d;
            color: white;
            border: none;
            padding: 18px 25px;
            border-radius: 50px;
            font-size: 1rem;
            cursor: pointer;
            width: 100%;
            font-weight: bold;
            box-shadow: 0 4px 15px rgba(255, 77, 109, 0.4);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        /* Contenedor del video invisible */
        #player-container {
            position: absolute;
            width: 1px;
            height: 1px;
            opacity: 0;
            pointer-events: none;
        }
    </style>
</head>
<body>

    <div id="player-container">
        <div id="player"></div>
    </div>

    <div class="container">
        <h1>Te amo Guada</h1>
        
        <div class="poema">
            Hoy te extrañé más que ayer, 
            se volvió mi hábito aunque sé que algún día voy a sanar...<br><br>
            Hoy prefiero disfrutar el pálpito de mi corazón al soñar 
            con tu hermosa alma y no quiero olvidar todos tus besos, 
            cuáles hacen de mis huesos olvidar que soy un humano más...<br><br>
            Pues son los mismos que me hacen volar 
            y al recapacitar de este sueño 
            me refuta que es real el amor que siento.
        </div>
        
        <button class="music-btn" onclick="playMusic()" id="btnText">
            <span>▶</span> REPRODUCIR CANCIÓN
        </button>
    </div>

    <script>
        // ID de Cafuné
        const videoId = 'MDSZK3PSjlY';
        let player;

        // Cargar API de YouTube
        var tag = document.createElement('script');
        tag.src = "https://www.youtube.com/iframe_api";
        var firstScriptTag = document.getElementsByTagName('script')[0];
        firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

        function onYouTubeIframeAPIReady() {
            player = new YT.Player('player', {
                height: '1',
                width: '1',
                videoId: videoId,
                playerVars: {
                    'playsinline': 1, // Vital para que funcione en móviles sin abrir la app
                    'controls': 0,
                    'disablekb': 1
                },
                events: {
                    'onReady': onPlayerReady
                }
            });
        }

        function onPlayerReady(event) {
            console.log("Reproductor listo");
        }

        function playMusic() {
            if (player && player.playVideo) {
                player.playVideo();
                document.getElementById('btnText').style.display = 'none'; // Oculta el botón tras dar play para que no estorbe
            }
        }
    </script>
</body>
</html>
