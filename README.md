<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Te amo Guada</title>
    <style>
        /* ESTILO NEGRO Y ROJO PROFUNDO */
        body {
            margin: 0;
            padding: 0;
            background: radial-gradient(circle, #3d0000 0%, #000000 100%);
            font-family: 'Georgia', serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            color: #ffffff;
            text-align: center;
        }

        .container {
            max-width: 85%;
            padding: 30px;
            background: rgba(0, 0, 0, 0.4);
            border-radius: 15px;
            border: 1px solid rgba(255, 77, 109, 0.3);
        }

        h1 {
            color: #ff4d6d;
            font-size: 2.2rem;
            margin-bottom: 20px;
            text-shadow: 0 0 15px rgba(255, 77, 109, 0.6);
            letter-spacing: 1px;
        }

        .poema {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #f0f0f0;
            font-style: italic;
            margin-bottom: 40px;
            white-space: pre-line; /* Mantiene los saltos de línea del poema */
        }

        /* BOTÓN DE MÚSICA */
        .music-btn {
            background-color: transparent;
            color: #ff4d6d;
            border: 2px solid #ff4d6d;
            padding: 15px 30px;
            border-radius: 50px;
            font-size: 0.9rem;
            cursor: pointer;
            transition: all 0.4s ease;
            text-transform: uppercase;
            font-weight: bold;
            letter-spacing: 2px;
        }

        .music-btn:hover {
            background-color: #ff4d6d;
            color: white;
            box-shadow: 0 0 25px rgba(255, 77, 109, 0.8);
            transform: scale(1.05);
        }

        #youtube-player {
            display: none;
        }
    </style>
</head>
<body>

    <div id="youtube-player"></div>

    <div class="container">
        <h1>Te amo Guada</h1>
        
        <div class="poema">
            Hoy te extrañé más que ayer, 
            se volvió mi hábito aunque sé que algún día voy a sanar 
            hoy prefiero disfrutar el pálpito de mi corazón al soñar 
            con tu hermosa alma y no quiero olvidar todos tus besos 
            cuáles hacen de mis huesos olvidar que soy un humano más 
            pues son los mismos que me hacen volar 
            y al recapacitar de este sueño 
            me refuta que es real el amor que siento
        </div>
        
        <button class="music-btn" onclick="toggleMusic()" id="musicControl">🎵 Escuchar nuestra canción</button>
    </div>

    <script>
        // ID de Micro TDH - Cafuné
        const YOUTUBE_VIDEO_ID = 'MDSZK3PSjlY'; 

        let player;
        let isPlaying = false;

        // API de YouTube
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
                btn.innerHTML = '⏸ Pausar Cafuné';
                isPlaying = true;
            } else {
                player.pauseVideo();
                btn.innerHTML = '🎵 Escuchar nuestra canción';
                isPlaying = false;
            }
        }
    </script>
</body>
</html>
