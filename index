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
      animation: fadeIn 1s ease-in-out forwards;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.95); }
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
    }

    .serendipia {
      font-size: 3em;
      font-weight: bold;
      color: #ff66b2;
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
    }

    svg {
      width: 350px;
      height: 350px;
    }

    .petalo {
      fill: none;
      stroke: yellow;
      stroke-width: 1;
      opacity: 0.7;
    }

    .centro {
      fill: brown;
    }

    .tallo {
      width: 20px;
      height: 150px;
      background: green;
      margin-top: -40px;
    }

    .flor:hover {
      transform: rotate(360deg);
      transition: transform 3s ease-in-out;
    }

    .flor {
      transition: transform 1s;
    }

    audio {
      display: none;
    }

  </style>
</head>
<body>

  <!-- 🎵 Música -->
  <audio autoplay loop>
    <source src="https://cdn.pixabay.com/audio/2022/03/15/audio_b1695b48e1.mp3" type="audio/mp3">
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
      🌼 En cada rincón donde miras, la primavera está escribiendo poesía con colores. 🌼
    </div>
    <div class="flor">
      <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
        <g transform="translate(100,100)">
          <g id="petalos"></g>
          <circle class="centro" r="20" />
        </g>
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
    }, 5000); // Después de 5s

    setTimeout(() => {
      document.getElementById('etapa2').classList.add('hidden');
      document.getElementById('corazones').classList.add('hidden');
      document.getElementById('girasol-container').style.display = 'flex';
      generarFlor();
    }, 8000); // Después de 5 + 3s

    // 🌻 Flor dinámica
    function generarFlor() {
      const svgNS = "http://www.w3.org/2000/svg";
      const group = document.getElementById("petalos");

      for (let i = 0; i < 36; i++) {
        const path = document.createElementNS(svgNS, "path");
        let d = "M0 0";

        for (let j = 0; j < 18; j++) {
          const r = 40 + j * 2;
          const angle = (Math.PI / 9);
          const x = r * Math.cos(angle);
          const y = r * Math.sin(angle);
          d += ` L ${x} ${y}`;
        }

        path.setAttribute("d", d);
        path.setAttribute("transform", `rotate(${i * 10})`);
        path.setAttribute("class", "petalo");
        group.appendChild(path);
      }
    }
  </script>

</body>
</html>
