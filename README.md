<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para Ti</title>
    <style>
        /* FONDO ROJO Y NEGRO MINIMALISTA */
        body {
            margin: 0;
            padding: 0;
            background: radial-gradient(circle, #2c0000 0%, #000000 100%);
            font-family: 'serif';
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: #ffffff;
            text-align: center;
        }

        .container {
            max-width: 80%;
            padding: 20px;
        }

        h1 {
            color: #ff4d6d;
            font-size: 2.5rem;
            margin-bottom: 20px;
            text-shadow: 0 0 10px rgba(255, 77, 109, 0.5);
        }

        p {
            font-size: 1.2rem;
            line-height: 1.6;
            color: #e0e0e0;
            margin-bottom: 30px;
        }

        /* BOTÓN DE MÚSICA */
        .music-btn {
            background-color: transparent;
            color: #ff4d6d;
            border: 2px solid #ff4d6d;
            padding: 12px 25px;
            border-radius: 30px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.4s ease;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .music-btn:hover {
            background-color: #ff4d6d;
            color: white;
            box-shadow: 0 0 20px rgba(255, 77, 109, 0.6);
        }

        #youtube-player {
            display: none;
        }
    </style>
</head>
<body>

    <div id="youtube-player"></div>

    <div class="container">
        <h1>Para [Su Nombre]</h1>
        
        <p>"Te extraño mi amor <br> 
        hoy te extrañé más que ayer, se volvió mi hábito aunque sé que algún día voy a sanar hoy prefiero disfrutar el pálpito de mi corazón al soñar con tu hermosa alma y no quiero olvidar todos tus besos cuáles hacen de mis huesos olvidar que soy un humano más pues son los mismos que me hacen volar y al recapacitar de este sueño me refuta que es real el amor que siento <br> 
        te amo."</p>
        
        <button class="music-btn" onclick="toggleMusic()" id="musicControl">🎵 Nuestra Canción</button>
    </div>

    <script>
        // --- Configuración de la Música (YouTube) ---
        // REEMPLAZA ESTO por el ID de tu video (lo que va después de v=)
        const YOUTUBE_VIDEO_ID = 'B-QClDztaO8&si=5fBcJtsch-kiPenM'; 

        let player;
        let isPlaying = false;

        var tag = document.createElement('script');
        tag.src = "https://www.youtube.com/iframe_api";
        var firstScriptTag = document.getElementsByTagName('script')[0];
        firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

        function onYouTubeIframeAPIReady() {
            player = new YT.Player('youtube-player', {
                height: '0',
                width: '0',
                videoId: YOUTUBE_VIDEO_ID,
                playerVars: {
                    'autoplay': 0,
                    'controls': 0,
                    'loop': 1,
                    'playlist': YOUTUBE_VIDEO_ID
                }
            });
        }

        function toggleMusic() {
            const btn = document.getElementById('musicControl');
            if (!player) return;

            if (!isPlaying) {
                player.playVideo();
                btn.innerHTML = '⏸ Pausar Música';
                isPlaying = true;
            } else {
                player.pauseVideo();
                btn.innerHTML = '🎵 Nuestra Canción';
                isPlaying = false;
            }
        }
    </script>
</body>
</html>
