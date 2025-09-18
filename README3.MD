<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Pago de Servicios</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-image: url("https://images5.alphacoders.com/648/648549.jpg");

            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 400px;
            margin: 60px auto;
            background: #fff;
            padding: 30px 40px 40px 40px;
            border-radius: 10px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
        }
        h2 {
            text-align: center;
            color: #333;
            margin-bottom: 24px;
        }
        label {
            display: block;
            margin-bottom: 8px;
            color: #555;
            font-weight: 600;
        }
        select, input[type="text"], input[type="number"], input[type="submit"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 18px;
            border: 1px solid #d7d7d7;
            border-radius: 5px;
            font-size: 16px;
        }
        input[type="submit"] {
            background: #0078d4;
            color: #fff;
            border: none;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.2s;
        }
        input[type="submit"]:hover {
            background: #005fa3;
        }
        .form-group {
            display: none;
        }
        .btn-regresar {
            display: block;
            width: 379px;
            padding: 10px;
            margin-top: 10px;
            background: #e0e0e0;
            color: #333;
            text-align: center;
            text-decoration: none;
            border-radius: 5px;
            font-weight: 600;
            border: 1px solid #bdbdbd;
            transition: background 0.2s;
        }
        .btn-pagar {
            display: block;
            width: 379px;
            padding: 10px;
            margin-top: 10px;
            background: #e0e0e0;
            color: #333;
            text-align: center;
            text-decoration: none;
            border-radius: 5px;
            font-weight: 600;
            border: 1px solid #bdbdbd;
            transition: background 0.2s;
}
        .btn-regresar:hover {
            background: #bdbdbd;
        }
    </style>
    <script>
        function mostrarFormulario() {
            const opcion = document.getElementById("servicio").value;
            document.querySelectorAll(".form-group").forEach(div => div.style.display = "none");
            if (opcion === "agua") {
                document.getElementById("form-agua").style.display = "block";
            } else if (opcion === "luz") {
                document.getElementById("form-luz").style.display = "block";
            } else if (opcion === "predio") {
                document.getElementById("form-predio").style.display = "block";
            } else if (opcion === "sat") {
                document.getElementById("form-sat").style.display = "block";
            }
        }
        window.onload = function() {
            document.getElementById("servicio").addEventListener("change", mostrarFormulario);
        };
    </script>
</head>
<body>
    <div class="container">
        <h2>Pagar Servicios</h2>
        <form>
            <label for="servicio">Selecciona el servicio:</label>
            <select id="servicio" name="servicio" required>
                <option value="">-- Elige una opción --</option>
                <option value="agua">Agua</option>
                <option value="luz">Luz CFE</option>
                <option value="predio">Predio</option>
                <option value="sat">Impuestos SAT</option>
            </select>

            <!-- Agua -->
            <div class="form-group" id="form-agua">
                <label for="nombreAgua">Nombre del titular:</label>
                <input type="text" id="nombreAgua" name="nombreAgua" placeholder="Nombre del titular" required>
                <label for="contratoAgua">Ruta o contrato:</label>
                <input type="text" id="contratoAgua" name="contratoAgua" placeholder="Ruta o contrato" required>
                <label for="montoAgua">Monto a pagar:</label>
                <input type="number" id="montoAgua" name="montoAgua" min="1" step="any" placeholder="Monto a pagar" required>
            </div>

            <!-- Luz CFE -->
            <div class="form-group" id="form-luz">
                <label for="nombreLuz">Nombre del titular:</label>
                <input type="text" id="nombreLuz" name="nombreLuz" placeholder="Nombre del titular" required>
                <label for="medidorLuz">Número de medidor:</label>
                <input type="text" id="medidorLuz" name="medidorLuz" placeholder="Número de medidor" required>
                <label for="montoLuz">Monto a pagar:</label>
                <input type="number" id="montoLuz" name="montoLuz" min="1" step="any" placeholder="Monto a pagar" required>
            </div>

            <!-- Predio -->
            <div class="form-group" id="form-predio">
                <label for="cuentaPredio">Número de cuenta:</label>
                <input type="text" id="cuentaPredio" name="cuentaPredio" placeholder="Número de cuenta" required>
                <label for="montoPredio">Monto a pagar:</label>
                <input type="number" id="montoPredio" name="montoPredio" min="1" step="any" placeholder="Monto a pagar" required>
            </div>

            <!-- Impuestos SAT -->
            <div class="form-group" id="form-sat">
                <label for="rfcSat">RFC:</label>
                <input type="text" id="rfcSat" name="rfcSat" placeholder="RFC" required>
                <label for="nombreSat">Nombre del titular:</label>
                <input type="text" id="nombreSat" name="nombreSat" placeholder="Nombre del titular" required>
                <label for="totalSat">Total a pagar:</label>
                <input type="number" id="totalSat" name="totalSat" min="1" step="any" placeholder="Total a pagar" required>
            </div>
            
        <a href="https://wallet.interledger-test.dev" class="btn-pagar">Elige tu wallet</a>
        </form>
        <a href="tiposervicio.html" class="btn-regresar">Regresar</a>
    </div>
</body>
</html>
