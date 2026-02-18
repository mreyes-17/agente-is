<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Expediente: Agente Santos</title>
    <link href="https://fonts.googleapis.com/css2?family=UnifrakturMaguntia&family=Special+Elite&family=Dancing+Script:wght@700&family=Playfair+Display:ital,wght@1,600&display=swap" rel="stylesheet">
    <style>
        :root {
            --paper: #fdfaf3;
            --ink: #2c2c2c;
            --rose: #a32d3c;
            --gold: #b08d57;
        }

        * { box-sizing: border-box; }

        body {
            background-color: #120a0a;
            margin: 0;
            padding: 10px;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            font-family: 'Special Elite', serif;
            min-height: 100vh;
            background-image: radial-gradient(circle, #2a1515 0%, #0a0505 100%);
        }

        .newspaper {
            width: 100%;
            max-width: 450px;
            background-color: var(--paper);
            background-image: url('https://www.transparenttextures.com/patterns/paper-fibers.png');
            padding: 20px;
            box-shadow: 0 0 50px rgba(0,0,0,0.8);
            border-radius: 2px;
            position: relative;
            border: 1px solid #e3d9c6;
            margin-bottom: 20px;
        }

        .page { display: none; animation: smoothReveal 0.8s ease-out; }
        .active { display: block; }

        @keyframes smoothReveal {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .header-main {
            text-align: center;
            border-bottom: 2px double var(--gold);
            margin-bottom: 20px;
            padding-bottom: 10px;
        }

        .edition-title {
            font-family: 'UnifrakturMaguntia', cursive;
            font-size: 2.2rem;
            color: var(--rose);
            margin: 5px 0;
        }

        .tagline {
            font-family: 'Playfair Display', serif;
            font-style: italic;
            font-size: 0.75rem;
            color: var(--gold);
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .photo-frame {
            background: #fff;
            padding: 8px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            margin: 15px 0;
            border: 1px solid #eee;
        }

        img, video { 
            width: 100%; 
            height: auto; 
            display: block; 
            border: 1px solid #ddd;
        }

        .handwritten {
            font-family: 'Dancing Script', cursive;
            color: var(--rose);
            font-size: 1.8rem;
            line-height: 1.1;
        }

        .btn-love {
            background: var(--rose);
            color: #fff;
            border: none;
            padding: 16px;
            width: 100%;
            font-family: 'Special Elite', serif;
            font-size: 1rem;
            text-transform: uppercase;
            cursor: pointer;
            border-radius: 4px;
            margin-top: 15px;
            box-shadow: 0 4px 10px rgba(163,45,60,0.3);
            transition: 0.3s;
        }

        .btn-love:active { transform: scale(0.98); }

        .quote-box {
            font-family: 'Playfair Display', serif;
            font-style: italic;
            font-size: 1rem;
            text-align: center;
            color: #444;
            padding: 12px;
            margin: 15px 0;
            border-left: 3px solid var(--rose);
            background: rgba(163,45,60,0.05);
            line-height: 1.4;
        }

        .falling {
            position: fixed;
            pointer-events: none;
            z-index: 9999;
            animation: fall linear forwards;
        }

        /* Estilo Carta Final */
        .final-letter {
            text-align: left;
            line-height: 1.6;
            font-size: 0.95rem;
            color: #2c2c2c;
        }

        @keyframes fall {
            to { transform: translateY(110vh) rotate(360deg); opacity: 0; }
        }
    </style>
</head>
<body>

    <audio id="bgMusic" loop>
        <source src="mi suerte.mp3" type="audio/mpeg">
    </audio>

    <div class="newspaper">

        <div class="page active" id="p1">
            <div style="text-align: center;">
                <span class="tagline">Confidencial // Nivel 5</span>
                <h1 class="edition-title">The Love Report</h1>
                
                <div style="margin: 20px 0; border-top: 1px solid var(--gold); border-bottom: 1px solid var(--gold); padding: 10px;">
                    <p style="font-size: 0.8rem; margin: 5px 0;">PARA: <br><span class="handwritten" style="font-size: 1.8rem;">Agente Santos</span></p>
                    <p style="font-size: 0.6rem; color: #777; margin: 5px 0;">DE: AGENTE M</p>
                </div>

                <p style="font-size: 0.9rem; line-height: 1.5;">Usted ha sido seleccionada para una misión de alta prioridad. Inicie el protocolo para revisar los hallazgos.</p>

                <button class="btn-love" onclick="startExperience()">INICIAR PROTOCOLO</button>
            </div>
        </div>

        <div class="page" id="p2">
            <div class="header-main">
                <span class="tagline">Anexo 01: Vigilancia</span>
                <h1 class="edition-title" style="font-size: 1.8rem;">Evidencia</h1>
            </div>
            
            <div class="photo-frame">
                <video id="v1" controls loop playsinline muted>
                    <source src="Video 1.mp4" type="video/mp4">
                </video>
            </div>
            
            <div class="quote-box">
                "Análisis: Se detecta felicidad absoluta en presencia del objetivo principal."
            </div>
            
            <button class="btn-love" onclick="nextPage(3)">SIGUIENTE PRUEBA</button>
        </div>

        <div class="page" id="p3">
            <h1 class="edition-title" style="font-size: 1.8rem; text-align: center;">Registros Visuales</h1>
            
            <div class="photo-frame" style="transform: rotate(1deg);">
                <img src="IM 1.jpg">
                <p class="handwritten" style="font-size: 1.2rem; text-align: center; margin-top: 8px;">Su sonrisa, Agente...</p>
            </div>

            <div class="photo-frame" style="transform: rotate(-1deg);">
                <img src="IM 2.jpg">
                <p class="handwritten" style="font-size: 1.2rem; text-align: center; margin-top: 8px;">...mi paz favorita.</p>
            </div>

            <button class="btn-love" onclick="nextPage(4)">VEREDICTO</button>
        </div>

        <div class="page" id="p4">
            <div class="header-main">
                <h1 class="edition-title" style="font-size: 1.8rem;">Veredicto Final</h1>
            </div>
            
            <div class="photo-frame">
                <img src="IM 3.jpg">
            </div>

            <p style="text-align: center; font-size: 0.9rem;">Solo una pregunta queda por responder para cerrar el caso:</p>
            
            <h2 class="handwritten" style="text-align: center; font-size: 2.2rem; margin: 15px 0;">¿Quieres ser mi San Valentín?</h2>
            
            <div style="background: var(--rose); color: white; padding: 12px; text-align: center; border-radius: 4px;">
                <p style="margin: 0; font-size: 0.8rem;">📅 <b>FECHA: 18 DE FEBRERO</b></p>
            </div>

            <button class="btn-love" onclick="celebrate()">¡SÍ, ACEPTO!</button>
        </div>

        <div class="page" id="p5">
            <div style="text-align: center;">
                <div class="photo-frame" style="border-radius: 50%; width: 140px; height: 140px; margin: 0 auto; overflow: hidden; border: 3px solid var(--rose);">
                    <img src="IM 5.jpg" style="height: 100%; object-fit: cover;">
                </div>
                <h1 class="handwritten" style="font-size: 2.2rem; margin-top: 15px;">¡Misión Aceptada!</h1>
                <div class="quote-box">
                    "Código San Valentín activado con éxito."
                </div>
                <p style="font-size: 0.85rem;">Para obtener las coordenadas finales, ingrese la clave de acceso.</p>
                
                <button class="btn-love" style="background: #333;" onclick="askPassword()">DESBLOQUEAR MAPA</button>
                
                <h2 class="handwritten" style="font-size: 2rem; margin-top: 20px;">TE AMA, M</h2>
            </div>
        </div>

        <div class="page" id="p6">
            <div class="header-main">
                <span class="tagline">Acceso Concedido</span>
                <h1 class="edition-title" style="font-size: 1.8rem;">La Cita</h1>
            </div>

            <div class="final-letter">
                <p class="handwritten" style="font-size: 2rem; margin-bottom: 5px;">Perfecto mi amor...</p>
                <p>Primero, <b>¡Feliz San Valentín!</b></p>
                <p>Has desbloqueado el lugar, pero la Agente Santos sabe que nada es tan simple. Para encontrarnos, busca el sitio donde el café y los vinilos conviven, un refugio lleno de tesoros <i>vintage</i>.</p>
                
                <div class="quote-box" style="background: #fff; border: 1px solid var(--gold); text-align: left;">
                    <p style="margin: 5px 0;">📍 <b>LUGAR:</b> <a href="https://maps.google.com/?q=-16.510985557152303,-68.12455033745351" target="_blank" style="color: var(--rose);">Tocar para ver mapa</a></p>
                    <p style="margin: 5px 0;">🕒 <b>HORA:</b> 17:30</p>
                </div>

                <p style="text-align: center; margin-top: 20px;">
                    Te espero allí.<br>
                    <span class="handwritten" style="font-size: 2rem;">Te ama, M</span>
                </p>
            </div>
        </div>

    </div>

    <script>
        const audio = document.getElementById('bgMusic');

        function startExperience() {
            audio.play().catch(() => {});
            nextPage(2);
        }

        function nextPage(n) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('p' + n).classList.add('active');
            window.scrollTo({top: 0, behavior: 'smooth'});
            if(n === 2) document.getElementById('v1').play().catch(() => {});
        }

        function celebrate() {
            nextPage(5);
            setInterval(createRain, 200);
        }

        function askPassword() {
            const pass = prompt("Para desbloquear:\n¿Cuál es el color favorito de M?");
            if (pass && pass.toLowerCase().trim() === "verde") {
                nextPage(6);
            } else if (pass !== null) {
                alert("Clave incorrecta.");
            }
        }

        function createRain() {
            const heart = document.createElement('div');
            heart.classList.add('falling');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.top = '-20px';
            heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
            heart.style.animationDuration = (Math.random() * 2 + 2) + 's';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 4000);
        }
    </script>
</body>
</html>
