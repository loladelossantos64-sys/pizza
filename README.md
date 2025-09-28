<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>¿Qué pizza eres?</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 20px;
      background: #fff3e0;
    }
    form {
      margin: 20px auto;
      max-width: 400px;
      text-align: left;
      background: #ffe0b2;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
    }
    button {
      margin-top: 15px;
      padding: 10px 20px;
      background: #ff7043;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 1em;
    }
    button:hover {
      background: #f4511e;
    }
    #resultado {
      margin-top: 20px;
      font-size: 1.3em;
      font-weight: bold;
      color: #d84315;
    }
  </style>
</head>
<body>
  <h1>🍕 ¿Qué pizza eres? 🍕</h1>
  <p>Responde las preguntas y descubre tu pizza ideal</p>

  <form id="pizzaForm">
    <!-- Pregunta 1 -->
    <label>1. ¿Qué sabor prefieres?</label><br>
    <select id="sabor" required>
      <option value="">Selecciona una opción</option>
      <option>Dulce</option>
      <option>Salado</option>
      <option>Picante</option>
    </select><br><br>

    <!-- Pregunta 2 -->
    <label>2. ¿Dónde te gusta más comer pizza?</label><br>
    <select id="plan" required>
      <option value="">Selecciona una opción</option>
      <option>En casa solo con pelis y manta</option>
      <option>En casa con amigos</option>
      <option>En la pizzería con amigas y chismosear</option>
      <option>En la pizzería con tu enamorada</option>
    </select><br><br>

    <!-- Pregunta 3 -->
    <label>3. ¿Qué ingrediente no puede faltar en tu pizza?</label><br>
    <select id="ingrediente1" required>
      <option value="">Selecciona una opción</option>
      <option>Queso extra</option>
      <option>Peperoni</option>
      <option>Verduras</option>
      <option>Piña</option>
      <option>Bacon</option>
      <option>Aceituna</option>
      <option>Carne</option>
      <option>Atún</option>
    </select><br><br>

    <!-- Pregunta 4 -->
    <label>4. ¿Qué ingrediente NO te gustaría que lleve tu pizza?</label><br>
    <select id="ingrediente2" required>
      <option value="">Selecciona una opción</option>
      <option>Queso</option>
      <option>Peperoni</option>
      <option>Verduras</option>
      <option>Piña</option>
      <option>Bacon</option>
      <option>Aceitunas</option>
      <option>Atún</option>
      <option>Carne</option>
    </select><br><br>

    <!-- Pregunta 5 -->
    <label>5. ¿Qué estación perfecta es para comer pizza?</label><br>
    <select id="estacion" required>
      <option value="">Selecciona una opción</option>
      <option>Todo el año</option>
      <option>Invierno</option>
      <option>Primavera</option>
      <option>Verano</option>
      <option>Otoño</option>
    </select><br><br>

    <button type="button" onclick="mostrarPizza()">Descubrir mi pizza</button>
  </form>

  <div id="resultado"></div>

  <script>
    function mostrarPizza() {
      const sabor = document.getElementById("sabor").value;
      const plan = document.getElementById("plan").value;
      const ingrediente1 = document.getElementById("ingrediente1").value;
      const ingrediente2 = document.getElementById("ingrediente2").value;
      const estacion = document.getElementById("estacion").value;

      // Validación de todas las preguntas
      if (!sabor || !plan || !ingrediente1 || !ingrediente2 || !estacion) {
        alert("Por favor, responde todas las preguntas.");
        return;
      }

      // Lista de pizzas
      const pizzas = [
        "🍕 **Pizza Margarita**: Simple, clásica y siempre confiable. ¡Como tú!",
        "🍍 **Pizza Hawaiana**: Dulce y atrevida, no todos te entienden, pero los que lo hacen te adoran.",
        "🌶️ **Pizza Diavola**: Picante y llena de energía, ¡siempre lista para la acción!",
        "🧀 **Pizza Cuatro Quesos**: Intensa y reconfortante, nunca pasas desapercibido.",
        "🥦 **Pizza Veggie**: Saludable, colorida y llena de buenas vibras.",
        "🍖 **Pizza Barbacoa**: Potente y sabrosa, eres la estrella de todas las reuniones.",
        "🍤 **Pizza de Mariscos**: Refinada y diferente, siempre sorprendes a los demás.",
        "🥩 **Pizza de Carne Suprema**: Fuerte y con carácter, no le temes a nada.",
        "🍄 **Pizza de Champiñones**: Tranquila y elegante, perfecta para los momentos zen.",
        "🍫 **Pizza Dulce**: Única y especial, porque no temes ser diferente.",
        "🌽 **Pizza Mexicana**: Alegre, llena de sabor y con un toque explosivo de picante.",
        "🥔 **Pizza de Patata y Bacon**: Confortable y acogedora, como un abrazo calientito."
      ];

      // Selección aleatoria
      const pizzaAleatoria = pizzas[Math.floor(Math.random() * pizzas.length)];

      // Mostrar resultado
      document.getElementById("resultado").innerHTML = `
        Según tus respuestas, eres:<br><br>
        <strong>${pizzaAleatoria}</strong>
      `;
    }
  </script>
</body>
</html>
