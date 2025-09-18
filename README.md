# Servicios-conectados
Todo el proyecto
Codigo HTML Interfaz principal
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Tipo de pago</title>
  <style>
    body {
      font-family: 'Segoe UI', Arial, sans-serif;
      margin: 0;
      padding: 0;
      min-height: 100vh;
      /* Fondo degradado animado */
      background: linear-gradient(135deg, #93f9b9 0%, #1d61a7 100%);
      animation: fondoGradiente 10s ease-in-out infinite alternate;
    }

    @keyframes fondoGradiente {
      0% {
        background: linear-gradient(135deg, #93f9b9 0%, #1d61a7 100%);
      }
      100% {
        background: linear-gradient(135deg, #ffdde1 0%, #6e7ff3 100%);
      }
    }

    .container {
      max-width: 900px;
      margin: 120px auto;
      background: rgba(255,255,255,0.92);
      padding: 100px 40px;
      border-radius: 80px;
      box-shadow: 0 8px 48px rgba(0,0,0,0.13);
      text-align: center;
      backdrop-filter: blur(2.5px);
    }
    h2 {
      margin-bottom: 32px;
      font-size: 5em;
      color: #23324C;
      letter-spacing: 2px;
      text-shadow: 0 4px 24px #c0c0f7;
    }
    .botones {
      display: flex;
      justify-content: center;
      gap: 56px;
      margin-bottom: 32px;
    }
    .boton-imagen {
      display: flex;
      flex-direction: column;
      align-items: center;
      background: none;
      border: none;
      cursor: pointer;
      padding: 0;
      outline: none;
      transition: transform 0.2s;
      text-decoration: none;
    }
    .boton-imagen img {
      width: 160px;
      height: 160px;
      object-fit: contain;
      border-radius: 20px;
      border: 3px solid #e0e0e0;
      margin-bottom: 18px;
      box-shadow: 0 2px 18px rgba(34,50,76,0.13);
      transition: border-color 0.2s, transform 0.2s;
    }
    .boton-imagen:focus img,
    .boton-imagen:hover img {
      border-color: #1d61a7;
      transform: scale(1.07);
    }
    .label {
      font-size: 1.35em;
      margin-top: 0;
      color: #2d363e;
      font-weight: 500;
      letter-spacing: 1px;
      text-shadow: 0 1px 8px #e2eafc;
    }
    .boton-regresar {
      display: inline-block;
      margin-top: 40px;
      padding: 18px 60px;
      font-size: 1.3em;
      font-weight: 600;
      color: #fff;
      background: linear-gradient(135deg, #1d61a7 0%, #93f9b9 100%);
      border: none;
      border-radius: 30px;
      box-shadow: 0 2px 12px rgba(34,50,76,0.13);
      cursor: pointer;
      text-decoration: none;
      transition: background 0.2s, transform 0.2s;
    }
    .boton-regresar:hover {
      background: linear-gradient(135deg, #6e7ff3 0%, #ffdde1 100%);
      transform: scale(1.05);
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Tipo de pago</h2>
    <div class="botones">
      <a class="boton-imagen" href="Iprivada.html" title="Privado">
        <img src="https://img.icons8.com/ios-filled/100/lock--v1.png" alt="Privado">
        <span class="label">Privado</span>
      </a>
      <a class="boton-imagen" href="Ipublica.html" title="Público">
        <img src="https://img.icons8.com/ios-filled/100/money-bag.png" alt="Público">
        <span class="label">Público</span>
      </a>
    </div>
    <a class="boton-regresar" href="https://wallet.interledger-test.dev/">Regresar</a>
  </div>
</body>
</html>
