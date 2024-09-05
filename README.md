# HOTEL-EPSILON
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gestión de Usuarios - Hotel</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        .container {
            width: 80%;
            margin: 20px auto;
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            text-align: center;
        }
        form {
            margin-bottom: 30px;
        }
        label {
            display: block;
            margin-bottom: 8px;
        }
        input, select {
            width: 100%;
            padding: 10px;
            margin-bottom: 20px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            background-color: #28a745;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 4px;
            cursor: pointer;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        table, th, td {
            border: 1px solid #ccc;
        }
        th, td {
            padding: 12px;
            text-align: left;
        }
        th {
            background-color: #28a745;
            color: white;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Gestión de Usuarios - Hotel</h1>

    <form id="userForm">
        <label for="nombre">Nombre:</label>
        <input type="text" id="nombre" name="nombre" required>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>

        <label for="telefono">Teléfono:</label>
        <input type="tel" id="telefono" name="telefono" required>

        <label for="tipo_habitacion">Tipo de Habitación:</label>
        <select id="tipo_habitacion" name="tipo_habitacion" required>
            <option value="Sencilla">Sencilla</option>
            <option value="Doble">Doble</option>
            <option value="Suite">Suite</option>
        </select>

        <button type="submit">Registrar Usuario</button>
    </form>

    <h2>Usuarios Registrados</h2>
    <table id="userTable">
        <thead>
            <tr>
                <th>Nombre</th>
                <th>Email</th>
                <th>Teléfono</th>
                <th>Tipo de Habitación</th>
            </tr>
        </thead>
        <tbody>
        </tbody>
    </table>
</div>

<script>
    document.getElementById('userForm').addEventListener('submit', function(event) {
        event.preventDefault();

        // Obtener los valores del formulario
        const nombre = document.getElementById('nombre').value;
        const email = document.getElementById('email').value;
        const telefono = document.getElementById('telefono').value;
        const tipoHabitacion = document.getElementById('tipo_habitacion').value;

        // Crear una nueva fila en la tabla
        const table = document.getElementById('userTable').getElementsByTagName('tbody')[0];
        const newRow = table.insertRow();

        const cellNombre = newRow.insertCell(0);
        const cellEmail = newRow.insertCell(1);
        const cellTelefono = newRow.insertCell(2);
        const cellTipoHabitacion = newRow.insertCell(3);

        cellNombre.textContent = nombre;
        cellEmail.textContent = email;
        cellTelefono.textContent = telefono;
        cellTipoHabitacion.textContent = tipoHabitacion;

        // Limpiar el formulario
        document.getElementById('userForm').reset();
    });
</script>

</body>
</html>
