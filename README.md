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
            width: 85%; /* Optimizado para móvil */
            max-width: 420px;
            background-color: var(--paper);
            background-image: url('https://www.transparenttextures.com/patterns/paper-fibers.png');
            padding: 25px; /* Menos padding para ganar espacio */
            margin: 20px 10px;
            box-shadow: 0 0 50px rgba(0,0,0,0.9);
            border-radius: 4px;
            position: relative;
            min-height: 85vh;
            border: 1px solid #e3d9c6;
        }

        .page { display: none; animation: smoothReveal 1.2s ease; }
        .active { display: block; }

        @keyframes smoothReveal {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .header-main {
            text-align: center;
            border-bottom: 2px solid var(--gold);
            margin-bottom: 20px;
            padding-bottom: 10px;
        }

        .edition-title {
            font-family: 'UnifrakturMaguntia', cursive;
            font-size: 2.5rem; /* Reducido para móvil */
            color: var(--rose);
            margin: 0;
        }

        .tagline {
            font-family: 'Playfair Display', serif;
            font-style: italic;
            font-size: 0.8rem;
            color: var(--gold);
            letter-spacing: 2px;
        }

        /* Puzzle Styling */
        .puzzle-container {
            background: #1a1a1a;
            color: #00ff00;
            padding: 15px;
            border-radius: 8px;
            font-family: monospace;
            font-size: 0.9rem;
            text-align: left;
            margin: 15px 0;
            border: 1px solid #333;
        }

        .puzzle-input {
            background: transparent;
            border: none;
            border-bottom: 2px solid #00ff00;
            color: #00ff00;
            font-size: 1.1rem;
            width: 100%;
            outline: none;
            margin-top: 10px;
            padding: 5px 0;
        }

        .photo-frame {
            background: #fff;
            padding: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            margin: 20px 0;
            border: 1px solid #f0e6d2;
        }

        img, video { width: 100%; height: auto; display: block; }

        .handwritten {
            font-family: 'Dancing Script', cursive;
            color: var(--rose);
            font-size: 2.2rem; /* Ajustado para móvil */
            line-height: 1.1;
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
            border-radius: 40px;
            margin-top: 20px;
            box-shadow: 0 5px 15px rgba(163,45,60,0.3);
            -webkit-tap-highlight-color: transparent; /* Quita flash azul en móvil */
        }

        .quote-box {
            font-family: 'Playfair Display', serif;
            font-style: italic;
            font-size: 1rem;
            text-align: center;
            color: #444;
            padding: 15px;
            margin: 15px 0;
            border-left: 3px solid var(--rose);
            background: rgba(163,45,60,0.03);
        }

        .falling {
            position: fixed;
            pointer-events: none;
            z-index: 1000;
            animation: fall linear forwards;
        }

        @keyframes fall {
            to { transform: translateY(100vh) rotate(360deg); opacity: 0; }
        }
    </style>
</head>
<body>

    <div class="newspaper">

        <div class="page active" id="p1">
            <div style="text-align: center; padding: 20px 0;">
                <span class="tagline">Top Secret // Solo para sus ojos</span>
                <h1 class="edition-title">The Love Report</h1>
                
                <div style="margin: 25px 0; border-top: 1px solid var(--gold); border-bottom: 1px solid var(--gold); padding: 10px;">
                    <p style="font-size: 0.9rem; margin: 5px 0;">DESTINATARIA: <br><span class="handwritten">Agente Santos</span></p>
                    <p style="font-size: 0.7rem; color: #777;">REMITENTE: M (SU AYUDANTE FIEL)</p>
                </div>

                <div class="music-container">
                    <iframe style="border-radius:12px" src="https://open.spotify.com/embed/track/2kVtMvrlcK5SRxZvdHgTzn?utm_source=generator" width="100%" height="152" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
                </div>

                <p style="font-size: 0.9rem; line-height: 1.5;">Active la música, Agente, y proceda con el descubrimiento.</p>

                <button class="btn-love" onclick="nextPage(2)">INICIAR DESBLOQUEO</button>
            </div>
        </div>

        <div class="page" id="p2">
            <div class="header-main">
                <span class="tagline">Seguridad Nivel 1</span>
                <h1 class="edition-title" style="font-size: 2rem;">Origen</h1>
            </div>
            <p style="font-size: 0.9rem;">Ingrese la clave de nuestra primera misión (el día que nos conocimos):</p>
            <div class="puzzle-container">
                <p>> STATUS: ENCRIPTADO</p>
                <p>> PISTA: DDMM</p>
                <input type="tel" id="passInput" class="puzzle-input" maxlength="4" placeholder="Ej: 0000">
                <p id="errorMsg1" style="color: #ff4444; display: none; font-size: 0.7rem; margin-top: 10px;">ERROR. Verifique la fecha inicial.</p>
            </div>
            <button class="btn-love" onclick="checkPuzzle1()">VALIDAR FECHA</button>
        </div>

        <div class="page" id="p3">
            <div class="header-main">
                <span class="tagline">Seguridad Nivel 2</span>
                <h1 class="edition-title" style="font-size: 2rem;">Identidad</h1>
            </div>
            <p style="font-size: 0.9rem;">¿Cómo la llama de cariño su ayudante M?</p>
            <div class="puzzle-container">
                <p>> IDENTIFICACIÓN REQUERIDA</p>
                <input type="text" id="nameInput" class="puzzle-input" placeholder="Nombre en clave...">
                <p id="errorMsg2" style="color: #ff4444; display: none; font-size: 0.7rem; margin-top: 10px;">Identidad no reconocida.</p>
            </div>
            <button class="btn-love" onclick="checkPuzzle2()">CONFIRMAR ACCESO</button>
        </div>

        <div class="page" id="p4">
            <div class="header-main">
                <span class="tagline">Anexo 01</span>
                <h1 class="edition-title" style="font-size: 2rem;">Evidencia Viva</h1>
            </div>
            <div class="photo-frame">
                <video id="v1" controls loop playsinline>
                    <source src="Video 1.mp4" type="video/mp4">
                </video>
            </div>
            <div class="quote-box">
                "Se observa una felicidad genuina que solo ocurre cuando usted está presente."
            </div>
            <button class="btn-love" onclick="nextPage(5)">SIGUIENTE HALLAZGO</button>
        </div>

        <div class="page" id="p5">
            <h1 class="edition-title" style="font-size: 2rem; text-align: center;">Evidencias</h1>
            <div class="photo-frame" style="transform: rotate(1deg);">
                <img src="IM 1.jpg">
                <p class="handwritten" style="font-size: 1.5rem; text-align: center; margin-top: 10px;">Su sonrisa...</p>
            </div>
            <div class="photo-frame" style="transform: rotate(-1deg);">
                <img src="IM 2.jpg">
                <p class="handwritten" style="font-size: 1.5rem; text-align: center; margin-top: 10px;">...mi paz favorita.</p>
            </div>
            <button class="btn-love" onclick="nextPage(6)">DICTAR SENTENCIA</button>
        </div>

        <div class="page" id="p6">
            <div class="header-main">
                <h1 class="edition-title">Veredicto</h1>
            </div>
            <div class="photo-frame"><img src="IM 3.jpg"></div>
            <h2 class="handwritten" style="text-align: center; font-size: 2.5rem; margin: 20px 0;">¿Puedo ser tu San Valentín?</h2>
            <div style="background: var(--rose); color: white; padding: 15px; text-align: center; border-radius: 12px;">
                <p style="margin: 0; font-size: 0.9rem;">📅 <b>MISIÓN: 18 DE FEBRERO</b></p>
            </div>
            <div style="display: flex; gap: 8px;">
                <button class="btn-love" onclick="celebrate()" style="font-size: 0.9rem;">SÍ, ACEPTO</button>
                <button class="btn-love" onclick="celebrate()" style="font-size: 0.9rem;">¡CLARO QUE SÍ!</button>
            </div>
        </div>

        <div class="page" id="p7">
            <div style="text-align: center; padding: 10px;">
                <div class="photo-frame" style="border-radius: 50%; width: 180px; height: 180px; margin: 0 auto; overflow: hidden; border: 4px solid var(--rose);">
                    <img src="IM 5.jpg" style="height: 100%; object-fit: cover;">
                </div>
                <h1 class="handwritten" style="font-size: 2.8rem; margin-top: 20px;">¡Misión Aceptada!</h1>
                <div class="quote-box">"La Agente Santos ha aceptado el primer caso de su carrera."</div>
                <h2 class="handwritten" style="font-size: 3rem;">TE AMA M</h2>
            </div>
        </div>

    </div>

    <script>
        function nextPage(n) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('p' + n).classList.add('active');
            window.scrollTo(0,0);
            if(n === 4) { document.getElementById('v1').play(); }
        }

        function checkPuzzle1() {
            if(document.getElementById('passInput').value === "0801") {
                nextPage(3);
            } else {
                document.getElementById('errorMsg1').style.display = 'block';
            }
        }

        function checkPuzzle2() {
            const val = document.getElementById('nameInput').value.toLowerCase().trim();
            if(val === "pinguinita" || val === "pingüinita") {
                nextPage(4);
            } else {
                document.getElementById('errorMsg2').style.display = 'block';
            }
        }

        function celebrate() {
            nextPage(7);
            setInterval(createSpecialRain, 150);
        }

        function createSpecialRain() {
            const symbols = ['💕', '💖', '🌷', '🐧'];
            const p = document.createElement('div');
            p.classList.add('falling');
            p.innerHTML = symbols[Math.floor(Math.random() * symbols.length)];
            p.style.left = Math.random() * 100 + 'vw';
            p.style.top = '-30px';
            p.style.fontSize = (Math.random() * 15 + 20) + 'px';
            p.style.animationDuration = (Math.random() * 2 + 2) + 's';
            document.body.appendChild(p);
            setTimeout(() => p.remove(), 4000);
        }
    </script>
</body>
</html>
