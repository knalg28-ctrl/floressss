<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>🌸 Proyecto Primavera</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', sans-serif;
      overflow: hidden;
      height: 100vh;
      background: #fff0f5;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
    }

    .hidden {
      display: none;
    }

    .fade-in {
      animation: fadeIn 2s ease-in-out forwards;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.8); }
      to { opacity: 1; transform: scale(1); }
    }

    .centered {
      position: absolute;
      text-align: center;
      padding: 20px;
    }

    .frase {
      font-size: 2em;
      color: #ff4081;
      animation: aparecer 2s ease-in-out;
    }

    .serendipia {
      font-size: 3em;
      font-weight: bold;
      color: #ff66b2;
      animation: aparecer 2s ease-in-out;
    }

    @keyframes aparecer {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .corazones {
      position: absolute;
      width: 100%;
      height: 100%;
      pointer-events: none;
      overflow: hidden;
    }

    .corazon {
      position: absolute;
      font-size: 2em;
      opacity: 0.6;
      animation: flotar 8s infinite ease-in;
    }

    @keyframes flotar {
      0% {
        transform: translateY(100vh) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) scale(1.5);
        opacity: 0;
      }
    }

    #girasol-container {
      position: absolute;
      top: 0;
      left: 0;
      background: black;
      color: white;
      width: 100vw;
      height: 100vh;
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }

    .header-text {
      color: white;
      font-size: 1.2em;
      margin-bottom: 30px;
      text-align: center;
      animation: aparecer 2s ease-in-out;
    }

    svg {
      width: 350px;
      height: 350px;
    }

    .petalo {
      fill: none;
      stroke: yellow;
      stroke-width: 1;
      opacity: 0.8;
      animation: girar 20s linear infinite;
      transform-origin: center;
    }

    @keyframes girar {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    .centro {
      fill: brown;
      animation: latir 2s infinite;
    }

    @keyframes latir {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.1); }
    }

.tallo {
      width: 30px;
      height: 200px;
      background: green;
      margin: 0 auto;
      margin-top: -40px;
      animation: crecer 2s ease-out forwards;
      transform: scaleY(0);
      transform-origin: top;
    }

    @keyframes crecer {
      from { transform: scaleY(0); }
      to { transform: scaleY(1); }
    }

    .flor {
      opacity: 0;
      animation: aparecerFlor 3s ease-in-out forwards;
      animation-delay: 1s;
      user-select: none;
    }

    @keyframes aparecerFlor {
      from { opacity: 0; transform: scale(0.5) rotate(-30deg); }
      to { opacity: 1; transform: scale(1) rotate(0deg); }
    }

    audio {
      display: none;
    }

    /* Botón para activar música */
    #activarMusica {
      position: absolute;
      top: 20px;
      right: 20px;
      z-index: 20;
      padding: 10px 15px;
      background: #ff69b4;
      color: white;
      border: none;
      border-radius: 8px;
      font-size: 1em;
      cursor: pointer;
      user-select: none;
      box-shadow: 0 0 10px #ff69b4;
      transition: background 0.3s;
    }
    #activarMusica:hover {
      background: #ff85c1;
    }
  </style>
</head>
<body>

  <!-- Botón para activar música manualmente -->
  <button id="activarMusica" aria-label="Activar música">🎵 Activar Música</button>

  <!-- 🎵 Música -->
  <audio id="musica" loop>
    <source src="https://cdn.pixabay.com/audio/2022/03/15/audio_b1695b48e1.mp3" type="audio/mp3" />
    Tu navegador no soporta audio.
  </audio>

  <!-- 🌸 ETAPA 1 -->
  <div class="centered frase" id="etapa1">
    🌸 Para la chica más linda que el destino me regaló 💖
  </div>

  <!-- 💫 ETAPA 2 -->
  <div class="centered serendipia hidden" id="etapa2">
    💫 SERENDIPIA 💫
  </div>

  <!-- 💖 Corazones flotantes -->
  <div class="corazones" id="corazones"></div>

  <!-- 🌻 ETAPA 3: FLOR -->
  <div id="girasol-container">
    <div class="header-text">
      🌼 Para vos con amor 🌼
    </div>
    <div class="flor">
      <svg viewBox="0 0 400 400" xmlns="http://www.w3.org/2000/svg">
        <g transform="translate(200,200)" id="petalos"></g>
        <circle class="centro" cx="200" cy="200" r="40" />
      </svg>
      <div class="tallo"></div>
    </div>
  </div>

  <!-- 🎯 SCRIPT -->
  <script>
    // 💖 Corazones flotantes
    const corazonesContainer = document.getElementById('corazones');
    const emojis = ['💖','💘','💕','❤️','🌸','💗','💞','🌷'];
    for (let i = 0; i < 25; i++) {
      const c = document.createElement('div');
      c.className = 'corazon';
      c.style.left = Math.random() * 100 + 'vw';
      c.style.animationDelay = (Math.random() * 8) + 's';
      c.innerText = emojis[Math.floor(Math.random() * emojis.length)];
      corazonesContainer.appendChild(c);
    }

    // 🕒 Transiciones automáticas
    setTimeout(() => {
      document.getElementById('etapa1').classList.add('hidden');
      document.getElementById('etapa2').classList.remove('hidden');
      document.getElementById('etapa2').classList.add('fade-in');
    }, 5000);

    setTimeout(() => {
      document.getElementById('etapa2').classList.add('hidden');
      document.getElementById('corazones').classList.add('hidden');
      document.getElementById('girasol-container').style.display = 'flex';
      generarFlor();
    }, 8000);

    // 🌻 Flor dinámica
    function generarFlor() {
      const svgNS = "http://www.w3.org/2000/svg";
      const group = document.getElementById("petalos");

      const numPetalos = 18; // número de pétalos

      for (let i = 0; i < numPetalos; i++) {
        for (let k = 0; k < 12; k++) {
          const petalo = document.createElementNS(svgNS, "ellipse");
          petalo.setAttribute("cx", 0);
          petalo.setAttribute("cy", -100);
          petalo.setAttribute("rx", 25 + k);
          petalo.setAttribute("ry", 80 + k*2);
          petalo.setAttribute("class", "petalo");
          petalo.setAttribute("transform", `rotate(${(360/numPetalos) * i})`);
          group.appendChild(petalo);
        }
      }
    }
  </script>

</body>
</html>
