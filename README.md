<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Invitación de Cumpleaños</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Alex+Brush&family=Montserrat:wght@300;400;500&display=swap');
  
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    
    body {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #f8f6f9;
      font-family: 'Montserrat', sans-serif;
      perspective: 1000px;
    }
    
    .envelope {
      width: 90%;
      max-width: 500px;
      aspect-ratio: 3/4;
      position: relative;
      transform-style: preserve-3d;
      transition: transform 1s ease;
      cursor: pointer;
    }
    
    .envelope.open {
      transform: rotateX(180deg);
    }
    
    .envelope-front, .invitation {
      position: absolute;
      inset: 0;
      width: 100%;
      height: 100%;
      backface-visibility: hidden;
      border-radius: 15px;
    }
    
    .envelope-front {
      background: linear-gradient(45deg, #9d4edd, #b185db);
      display: flex;
      justify-content: center;
      align-items: center;
      box-shadow: 0 10px 30px rgba(0,0,0,0.2);
      z-index: 1;
      font-size: 1.5em;
      color: white;
    }
    
    .invitation {
      background: white;
      transform: rotateX(180deg);
      padding: 2rem;
      text-align: center;
      box-shadow: 0 10px 30px rgba(0,0,0,0.15);
      overflow: hidden;
    }

    .side-flower {
      position: absolute;
      width: 40px;
      height: 40px;
      opacity: 0.8;
    }

    .side-flower::before {
      content: '✿';
      position: absolute;
      font-size: 30px;
      color: #9d4edd;
      animation: sideFloat 3s infinite ease-in-out;
    }

    .side-flower:nth-child(1) { left: 10px; top: 20%; }
    .side-flower:nth-child(2) { left: 15px; top: 50%; animation-delay: 0.5s; }
    .side-flower:nth-child(3) { left: 5px; top: 80%; animation-delay: 1s; }
    .side-flower:nth-child(4) { right: 10px; top: 20%; }
    .side-flower:nth-child(5) { right: 15px; top: 50%; animation-delay: 0.5s; }
    .side-flower:nth-child(6) { right: 5px; top: 80%; animation-delay: 1s; }

    .butterfly {
      position: absolute;
      width: 20px;
      height: 20px;
    }

    .butterfly::before {
      content: '🦋';
      position: absolute;
      font-size: 20px;
      color: #9d4edd;
      animation: flutter 4s infinite ease-in-out;
    }

    @keyframes sideFloat {
      0%, 100% { transform: translateX(0); }
      50% { transform: translateX(10px); }
    }

    @keyframes flutter {
      0%, 100% { transform: translate(0, 0) rotate(0deg); }
      25% { transform: translate(5px, -5px) rotate(10deg); }
      50% { transform: translate(0, -10px) rotate(-10deg); }
      75% { transform: translate(-5px, -5px) rotate(10deg); }
    }

    .click-prompt {
      font-family: 'Alex Brush', cursive;
      font-size: 2.5em;
      color: white;
      text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2);
    }

    .floral-frame {
      position: relative;
      margin-top: 20px;
    }
    
    .flower {
      position: relative;
      display: inline-block;
      margin: 20px;
    }

    .flower .butterfly {
      animation-duration: 6s;
    }

    .flower:nth-child(1) .butterfly {
      animation-delay: 1s;
    }

    .flower:nth-child(2) .butterfly {
      animation-delay: 2s;
    }

    .flower:nth-child(3) .butterfly {
      animation-delay: 3s;
    }

    .flower:nth-child(4) .butterfly {
      animation-delay: 4s;
    }
    
  </style>
</head>
<body>
  <div class="envelope" onclick="this.classList.toggle('open')">
    <div class="envelope-front">
      <div class="click-prompt">¡Haz clic para abrir!</div>
    </div>
    <div class="invitation">
      <div class="side-flower"></div>
      <div class="side-flower"></div>
      <div class="side-flower"></div>
      <div class="side-flower"></div>
      <div class="side-flower"></div>
      <div class="side-flower"></div>

      <div class="floral-frame">
        <div class="flower">
          <div class="butterfly"></div>
        </div>
        <div class="flower">
          <div class="butterfly"></div>
        </div>
        <div class="flower">
          <div class="butterfly"></div>
        </div>
        <div class="flower">
          <div class="butterfly"></div>
        </div>
      </div>

      <div>
        <h2 style="font-family: 'Alex Brush', cursive; color: #9d4edd;">¡Estás invitado!</h2>
        <p style="font-size: 1.5em;">Acompáñame a celebrar mi cumpleaños</p>
        <p style="font-size: 1.2em; color: #9d4edd;">El 20 de Enero a las 19:00 hrs</p>
        <p style="font-size: 1em; color: #9d4edd;">Dirección: Calle [Tu Dirección]</p>
      </div>
    </div>
  </div>
</body>
</html>
