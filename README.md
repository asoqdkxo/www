<!DOCTYPE html><!-- DOCTYPE bleibt notwendig, wird aber nicht angezeigt -->
<html lang="de">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>💖 Valentine 💖</title>
  <style>
    * {
      box-sizing: border-box;
      font-family: Arial, Helvetica, sans-serif;
    }

    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(180deg, #ff9a9e, #fad0c4);
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
    }

    .card {
      background: white;
      width: 90%;
      max-width: 380px;
      padding: 25px;
      border-radius: 25px;
      text-align: center;
      box-shadow: 0 15px 30px rgba(0,0,0,0.2);
      position: relative;
      z-index: 2;
    }

    h1 {
      color: #ff2f92;
      font-size: 26px;
      margin-bottom: 30px;
    }

    .buttons {
      position: relative;
      height: 120px;
      margin-top: 20px;
    }

    button {
      border: none;
      padding: 14px 22px;
      font-size: 18px;
      border-radius: 25px;
      cursor: pointer;
    }

    #yes {
      background: #ff2f92;
      color: white;
      position: absolute;
      left: 0;
      top: 20px;
    }

    #no {
      background: #ffd6e8;
      color: #444;
      position: absolute;
      right: 0;
      top: 20px;
    }

    .float {
      position: absolute;
      bottom: -80px;
      font-size: 32px;
      animation: floatUp 6s linear forwards;
      pointer-events: none;
    }

    @keyframes floatUp {
      from { transform: translateY(0); opacity: 1; }
      to { transform: translateY(-120vh); opacity: 0; }
    }

    .message {
      position: absolute;
      top: 40%;
      width: 100%;
      text-align: center;
      font-size: 28px;
      color: white;
      font-weight: bold;
      z-index: 3;
    }
  </style>
</head>
<body>

  <div class="card" id="card">
    <h1>Du Kleiner KELBBBBB 💖</h1>
    <div class="buttons">
      <button id="yes" onclick="sayYes()">Yes 😍</button>
      <button id="no">No 🙃</button>
    </div>
  </div>

  <script>
    const noBtn = document.getElementById('no');
    const btnArea = document.querySelector('.buttons');

    function moveNo() {
      const maxX = btnArea.offsetWidth - noBtn.offsetWidth;
      const maxY = btnArea.offsetHeight - noBtn.offsetHeight;
      noBtn.style.left = Math.random() * maxX + 'px';
      noBtn.style.top = Math.random() * maxY + 'px';
    }

    noBtn.addEventListener('touchstart', moveNo);
    noBtn.addEventListener('mouseover', moveNo);

    function sayYes() {
      document.getElementById('card').style.display = 'none';

      const msg = document.createElement('div');
      msg.className = 'message';
      msg.innerText = 'Das ist der beste Tag meines Lebens ❤️';
      document.body.appendChild(msg);

      for (let i = 0; i < 40; i++) {
        setTimeout(createFloat, i * 150);
      }
    }

    function createFloat() {
      const el = document.createElement('div');
      el.className = 'float';
      el.innerText = Math.random() > 0.5 ? '🇦🇫/❤️☀️💚' : '♾️❤️';
      el.style.left = Math.random() * 100 + 'vw';
      document.body.appendChild(el);
      setTimeout(() => el.remove(), 6000);
    }
  </script>

</body>
</html>
