<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>INTERFAZ PRIVADA</title>
  <style>
    body {
      font-family: 'Segoe UI', Arial, sans-serif;
      background-image: url("https://c4.wallpaperflare.com/wallpaper/1001/29/71/tecnologia-wallpaper-preview.jpg");
      background-size: cover;
      color: #222;
      margin: 0;
      padding: 0;
    }
    .container {
      max-width: 420px;
      margin: 40px auto;
      background: #fff;
      border-radius: 12px;
      box-shadow: 0 6px 24px rgba(0,0,0,0.10);
      padding: 32px;
    }
    h1 {
      color: #4a90e2;
      text-align: center;
      margin-bottom: 24px;
    }
    label {
      font-weight: 500;
      margin-bottom: 6px;
      display: block;
    }
    select, input[type="text"], input[type="number"] {
      width: 100%;
      padding: 7px 10px;
      margin-bottom: 15px;
      border-radius: 6px;
      border: 1px solid #ccd;
      font-size: 1em;
      background: #fafbff;
      transition: border-color 0.2s;
    }
    select:focus, input[type="text"]:focus, input[type="number"]:focus {
      border-color: #4a90e2;
      outline: none;
    }
    .questionnaire {
      margin-top: 18px;
      background: #f9fafe;
      border-radius: 8px;
      padding: 18px 14px 8px 14px;
      box-shadow: 0 2px 8px rgba(66,133,244,0.07);
    }
    .back-link {
      display: block;
      margin-top: 30px;
      text-align: center;
      color: #4a90e2;
      text-decoration: none;
      font-weight: 500;
      font-size: 1.04em;
    }
    .back-link:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Operación que quiere pagar</h1>

    <label for="opciones">Selecciona una opción:</label>
    <select id="opciones">
      <option value="">-- Elige una opción --</option>
      <option value="Streaming">Streaming</option>
      <option value="Compras">Compras en línea</option>
      <option value="Aseguradoras">Aseguradoras</option>
      <option value="Tarjetas">Tarjetas de crédito</option>
      <!-- <option value="PagoTarjeta">Pago de tarjeta</option> Eliminado -->
    </select>

    <div id="cuestionario" class="questionnaire" style="display:none;"></div>
    <a href="https://wallet.interledger-test.dev/" class="back-link">Elige tu wallet</a>
    <a href="tiposervicio.html" class="back-link">Regresar a la página principal</a>
  </div>

  <script>
    const cuestionarios = {
      Streaming: [
        { label: "Plataforma de Streaming", name: "plataforma", type: "select", options: ["Vix", "Netflix", "Prime", "Max"] },
        { label: "Numero de cuenta", name: "num_cuenta", type: "text" },
        { label: "Monto a pagar", name: "monto", type: "number" }
      ],
      Compras: [
        { label: "Numero de folio", name: "tienda", type: "text" },
        { label: "Cuenta", name: "num_cuenta", type: "text" },
        { label: "Monto a pagar", name: "monto", type: "number" }
      ],
      Aseguradoras: [
        { label: "Numero de folio", name: "num_cuenta", type: "text" },
        { label: "Monto a pagar", name: "monto", type: "number" }
      ],
      Tarjetas: [
        { label: "Nombre del banco", name: "num_tarjeta", type: "text" },
        { label: "Numero de cuenta", name: "num_cuenta", type: "text" },
        { label: "Monto a pagar", name: "monto", type: "number" }
      ]
      // PagoTarjeta eliminado del objeto de cuestionarios
    };

    const select = document.getElementById('opciones');
    const cuestionarioDiv = document.getElementById('cuestionario');

    select.addEventListener('change', function() {
      const value = select.value;
      if (cuestionarios[value]) {
        cuestionarioDiv.style.display = 'block';
        cuestionarioDiv.innerHTML = `
          <strong>Cuestionario: ${select.options[select.selectedIndex].text}</strong><br><br>
          ${cuestionarios[value].map(campo => {
            if (campo.type === "select") {
              return `
                <label>${campo.label}</label>
                <select name="${campo.name}">
                  ${campo.options.map(op => `<option value="${op}">${op}</option>`).join('')}
                </select><br>
              `;
            } else {
              return `
                <label>${campo.label}</label>
                <input type="${campo.type}" name="${campo.name}" /><br>
              `;
            }
          }).join('')}
        `;
      } else {
        cuestionarioDiv.style.display = 'none';
        cuestionarioDiv.innerHTML = '';
      }
    });
  </script>
</body>
</html>
