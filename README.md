<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Nosso Amor</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #ffe6f0;
      text-align: center;
      padding: 40px;
    }

    h1 {
      font-size: 2.5em;
      color: #d63384;
    }

    #timer {
      font-size: 1.8em;
      margin-top: 20px;
      color: #333;
      display: none;
    }

    button {
      background-color: #ff4d79;
      color: white;
      border: none;
      padding: 15px 30px;
      font-size: 1.2em;
      border-radius: 10px;
      cursor: pointer;
    }

    button:hover {
      background-color: #e0436d;
    }

    img {
      margin-top: 30px;
      width: 300px;
      max-width: 90%;
      border-radius: 15px;
      display: none;
    }

    #fraseRomantica {
      display: none;
      margin-top: 40px;
      font-size: 1.5em;
      color: #d63384;
    }
  </style>
</head>
<body>
  <h1>QUER SABER QUANTO TEMPO VC ME ATURA?</h1>
  <button id="loveButton">CLICA AQUI</button>
  <div id="timer"></div>
  <img id="foto" src="nosso_amor.jpg" alt="Nossa foto juntos" />

  <!-- Frase romântica -->
  <p id="fraseRomantica">
    E que cada segundo ao seu lado seja apenas o começo da nossa eternidade juntos.
  </p>

  <!-- Música -->
  <audio id="musica" src="ordinary.mp3"></audio>

  <script>
    const dataInicial = new Date("2024-10-08T00:00:00"); // Altere a data aqui
    const botao = document.getElementById("loveButton");
    const timer = document.getElementById("timer");
    const foto = document.getElementById("foto");
    const musica = document.getElementById("musica");
    const frase = document.getElementById("fraseRomantica");

    function atualizarCronometro() {
      const agora = new Date();
      const diff = agora - dataInicial;

      const dias = Math.floor(diff / (1000 * 60 * 60 * 24));
      const horas = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutos = Math.floor((diff / (1000 * 60)) % 60);
      const segundos = Math.floor((diff / 1000) % 60);

      timer.textContent = `${dias} dias, ${horas} horas, ${minutos} minutos e ${segundos} segundos juntos`;
    }

    botao.addEventListener("click", () => {
      botao.style.display = "none";
      timer.style.display = "block";
      foto.style.display = "block";
      musica.play();
      frase.style.display = "block"; // Mostra a frase romântica
      atualizarCronometro();
      setInterval(atualizarCronometro, 1000);
    });
  </script>
</body>
</html>