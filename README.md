<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Expediente Confidencial: Agente Santos</title>
    <link href="https://fonts.googleapis.com/css2?family=UnifrakturMaguntia&family=Special+Elite&family=Dancing+Script:wght@700&family=Playfair+Display:ital,wght@1,600&display=swap" rel="stylesheet">
    <style>
        :root {
            --paper: #fdfaf3;
            --ink: #2c2c2c;
            --rose: #a32d3c;
            --gold: #b08d57;
        }

        body {
            background-color: #120a0a;
            margin: 0;
            display: flex;
            justify-content: center;
            font-family: 'Special Elite', serif;
            overflow-x: hidden;
            background-image: radial-gradient(circle, #2a1515 0%, #0a0505 100%);
        }

        .newspaper {
            width: 85%;
            max-width: 480px;
            background-color: var(--paper);
            background-image: url('https://www.transparenttextures.com/patterns/paper-fibers.png');
            padding: 25px;
            margin: 20px 0;
            box-shadow: 0 0 80px rgba(0,0,0,0.9), inset 0 0 100px rgba(176,141,87,0.1);
            border-radius: 4px;
            position: relative;
            min-height: 90vh;
            border: 1px solid #e3d9c6;
        }

        .page { display: none; animation: smoothReveal 1.5s ease; }
        .active { display: block; }

        @keyframes smoothReveal {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .header-main {
            text-align: center;
            border-bottom: 2px solid var(--gold);
            margin-bottom: 30px;
            padding-bottom: 15px;
        }

        .edition-title {
            font-family: 'UnifrakturMaguntia', cursive;
            font-size: 2.8rem;
            color: var(--rose);
            margin: 0;
        }

        .tagline {
            font-family: 'Playfair Display', serif;
            font-style: italic;
            font-size: 0.9rem;
            color: var(--gold);
            letter-spacing: 3px;
        }

        .photo-frame {
            background: #fff;
            padding: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            margin: 20px 0;
            border: 1px solid #f0e6d2;
            transform: rotate(-0.5deg);
        }

        img, video { width: 100%; height: auto; border-radius: 1px; display: block; }

        .handwritten {
            font-family: 'Dancing Script', cursive;
            color: var(--rose);
            font-size: 2.2rem;
            line-height: 1.2;
        }

        .btn-love {
            background: var(--rose);
            color: #fdfaf3;
            border: none;
            padding: 18px;
            width: 100%;
            font-family: 'Special Elite', serif;
            font-size: 1rem;
            cursor: pointer;
            border-radius: 50px;
            margin-top: 25px;
            box-shadow: 0 10px 25px rgba(163,45,60,0.4);
            transition: 0.4s;
            letter-spacing: 1px;
            -webkit-tap-highlight-color: transparent;
        }

        .btn-unlock { background: #2c2c2c; margin-top: 15px; }

        .quote-box {
            font-family: 'Playfair Display', serif;
            font-style: italic;
            font-size: 1.1rem;
            text-align: center;
            color: #444;
            padding: 15px;
            margin: 15px 0;
            border-left: 4px solid var(--rose);
            background: rgba(163,45,60,0.03);
        }

        .falling {
            position: fixed;
            pointer-events: none;
            z-index: 1000;
            animation: fall linear forwards;
        }

        .final-letter { text-align: left; line-height: 1.8; font-size: 1.1rem; color: #333; }

        @keyframes fall {
            to { transform: translateY(100vh) rotate(360deg); opacity: 0; }
        }
    </style>
</head>
<body>

    <audio id="bgMusic" loop>
        <source src="mi suerte.mp3" type="audio/mpeg">
    </audio>

    <div class="newspaper">

        <div class="page active" id="p1">
            <div style="text-align: center; padding: 20px 0;">
                <span class="tagline">Top Secret // Solo para sus ojos</span>
                <h1 class="edition-title">The Love Report</h1>
                
                <div style="margin: 25px 0; border-top: 1px solid var(--gold); border-bottom: 1px solid var(--gold); padding: 15px;">
                    <p style="letter-spacing: 1px; font-size: 0.9rem;">DESTINATARIA: <br><span class="handwritten" style="font-size: 2rem;">Agente Santos</span></p>
                    <p style="font-size: 0.7rem; color: #777;">REMITENTE: M (SU AYUDANTE FIEL)</p>
                </div>

                <p style="line-height: 1.6; font-size: 0.95rem;">Usted ha sido seleccionada para revisar una serie de hallazgos críticos. Por favor, <b>Agente Santos</b>, presione el botón para iniciar la secuencia.</p>

                <button class="btn-love" onclick="startExperience()">INICIAR MISIÓN</button>
            </div>
        </div>

        <div class="page" id="p2">
            <div class="header-main">
                <span class="tagline">Anexo de Vigilancia 01</span>
                <h1 class="edition-title" style="font-size: 2rem;">Evidencia Viva</h1>
            </div>
            
            <div class="photo-frame">
                <video id="v1" controls loop playsinline>
                    <source src="Video 1.mp4" type="video/mp4">
                </video>
            </div>
            
            <div class="quote-box">
                "Se observa una felicidad genuina que solo ocurre cuando usted está presente en la escena."
            </div>
            
            <button class="btn-love" onclick="nextPage(3)">SIGUIENTE HALLAZGO</button>
        </div>

        <div class="page" id="p3">
            <h1 class="edition-title" style="font-size: 2rem; text-align: center;">Momentos Capturados</h1>
            
            <div class="photo-frame" style="transform: rotate(1.5deg);">
                <img src="IM 1.jpg">
                <p class="handwritten" style="font-size: 1.4rem; text-align: center; margin-top: 10px;">Su sonrisa, Agente...</p>
            </div>

            <div class="photo-frame" style="transform: rotate(-1.5deg);">
                <img src="IM 2.jpg">
                <p class="handwritten" style="font-size: 1.4rem; text-align: center; margin-top: 10px;">...es mi paz favorita.</p>
            </div>

            <button class="btn-love" onclick="nextPage(4)">DICTAR SENTENCIA</button>
        </div>

        <div class="page" id="p4">
            <div class="header-main">
                <h1 class="edition-title" style="font-size: 2.2rem;">Veredicto Final</h1>
            </div>
            
            <div class="photo-frame">
                <img src="IM 3.jpg">
            </div>

            <p style="text-align: center; padding: 0 5px; font-size: 0.95rem;">Tras una investigación profunda, solo queda una interrogante para la <b>Agente Santos</b>:</p>
            
            <h2 class="handwritten" style="text-align: center; font-size: 2.5rem; margin: 20px 0;">¿Puedo ser tu San Valentín?</h2>
            
            <div style="background: var(--rose); color: white; padding: 15px; text-align: center; border-radius: 15px; box-shadow: 0 5px 15px rgba(0,0,0,0.2);">
                <p style="margin: 0; font-size: 0.9rem;">📅 <b>MISIÓN CONFIRMADA: 18 DE FEBRERO</b></p>
            </div>

            <div style="display: flex; gap: 8px;">
                <button class="btn-love" onclick="celebrate()" style="font-size: 0.9rem; padding: 15px 5px;">SÍ, ACEPTO</button>
                <button class="btn-love" onclick="celebrate()" style="font-size: 0.9rem; padding: 15px 5px;">¡CLARO QUE SÍ!</button>
            </div>
        </div>

        <div class="page" id="p5">
            <div style="text-align: center; padding: 10px;">
                <div class="photo-frame" style="border-radius: 50%; width: 180px; height: 180px; margin: 0 auto; overflow: hidden; border: 4px solid var(--paper);">
                    <img src="IM 5.jpg" style="height: 100%; object-fit: cover;">
                </div>
                <h1 class="handwritten" style="font-size: 2.8rem; margin-top: 20px;">¡Misión Aceptada!</h1>
                <div class="quote-box">
                    "La Agente Santos ha aceptado el primer caso de su carrera: Ser mi San Valentín."
                </div>
                <p style="font-size: 0.9rem;">Para conocer el destino de la misión, ingrese la clave de seguridad.</p>
                
                <button class="btn-love btn-unlock" onclick="askPassword()">DESBLOQUEAR UBICACIÓN</button>
                
                <br><br>
                <h2 class="handwritten" style="font-size: 2.8rem;">TE AMA M</h2>
            </div>
        </div>

        <div class="page" id="p6">
            <div class="header-main">
                <span class="tagline">Coordenadas Desbloqueadas</span>
                <h1 class="edition-title" style="font-size: 2.2rem;">Instrucciones Finales</h1>
            </div>

            <div class="final-letter">
                <p class="handwritten" style="font-size: 2.5rem; color: var(--rose); margin-bottom: 10px;">Perfecto, mi amor...</p>
                <p>Primero que nada, <b>¡Feliz San Valentín!</b></p>
                <p>Como ves, el lugar de nuestra cita se ha desbloqueado, pero... ¿creíste que sería tan fácil? Pues no. Para encontrarme, deberás seguir tu instinto.</p>
                <p>Dirígete al lugar donde el aroma del café y los discos se encuentran; ese rincón especial donde en cada esquina encuentras tesoros <i>vintage</i>.</p>
                
                <div class="quote-box" style="border-left: 4px solid var(--gold); background: #fff;">
                    <strong>PUNTO DE ENCUENTRO:</strong><br>
                    📍 <a href="https://www.google.com/maps?q=-16.510985557152303,-68.12455033745351" target="_blank" style="color: var(--rose); text-decoration: underline;">Ver en Google Maps</a><br>
                    <strong>COORDENADAS:</strong> -16.510985, -68.124550<br>
                    <strong>HORA:</strong> 17:30
                </div>

                <p style="text-align: center; margin-top: 30px;">
                    Te espero allí con ansias.<br>
                    <span class="handwritten" style="font-size: 2.5rem;">Te ama, M</span>
                </p>
            </div>
        </div>

    </div>

    <script>
        const audio = document.getElementById('bgMusic');

        function startExperience() {
            // Reproducir música al primer clic (requisito del navegador)
            audio.play().catch(e => console.log("Error al reproducir audio"));
            nextPage(2);
        }

        function nextPage(n) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('p' + n).classList.add('active');
            window.scrollTo({top: 0, behavior: 'smooth'});
            
            if(n === 2) { 
                const v = document.getElementById('v1');
                v.play().catch(e => console.log("Video bloqueado")); 
            }
        }

        function celebrate() {
            nextPage(5);
            setInterval(createSpecialRain, 150);
        }

        function askPassword() {
            const pass = prompt("PROTOCOLOS DE SEGURIDAD:\n¿Cuál es el color favorito de M?");
            if (pass && pass.toLowerCase().trim() === "verde") {
                nextPage(6);
            } else if (pass !== null) {
                alert("Clave incorrecta. El acceso permanece restringido.");
            }
        }

        function createSpecialRain() {
            const symbols = ['💕', '💖', '🌷', '✨'];
            const p = document.createElement('div');
            p.classList.add('falling');
            p.innerHTML = symbols[Math.floor(Math.random() * symbols.length)];
            p.style.left = Math.random() * 100 + 'vw';
            p.style.top = '-20px';
            p.style.fontSize = (Math.random() * 15 + 20) + 'px';
            p.style.animationDuration = (Math.random() * 3 + 2) + 's';
            document.body.appendChild(p);
            setTimeout(() => p.remove(), 5000);
        }
    </script>
</body>
</html>
