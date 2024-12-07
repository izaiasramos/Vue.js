<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Vue.js Input Example</title>
  <script src="https://cdn.jsdelivr.net/npm/vue@2"></script>
</head>
<body>
  <div id="app">
    <!-- Campo de entrada -->
    <label for="userInput">Digite algo:</label>
    <input type="text" id="userInput" v-model="message" placeholder="Escreva aqui">

    <!-- Exibição do valor -->
    <p>Você digitou: {{ message }}</p>
  </div>

  <script>
    new Vue({
      el: '#app',
      data: {
        message: '' // Variável para armazenar o valor do input
      }
    });
  </script>
</body>
</html>
