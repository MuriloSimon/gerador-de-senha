<!DOCTYPE html>
<html lang="pt-br">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gerador de Senha</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f4f4f4;
    }

    .container {
      margin-top: 50px;
    }

    h2 {
      color: #333;
    }

    input[type="number"] {
      width: 50px;
      padding: 5px;
      text-align: center;
    }

    label {
      margin-right: 10px;
    }

    #password {
      margin-top: 20px;
      font-size: 24px;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
      display: inline-block;
      background-color: #fff;
      min-width: 200px;
    }

    button {
      font-size: 1em;
      padding: 10px 20px;
      margin-top: 20px;
      background-color: #007bff;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    button:hover {
      background-color: #0056b3;
    }
  </style>
</head>

<body>
  <div class="container">
    <h2>Gerador de Senha Segura</h2>
    <form id="passwordForm">
      <label for="length">Comprimento:</label>
      <input type="number" id="length" min="4" max="30" value="12">
      <br><br>
      <input type="checkbox" id="uppercase" checked>
      <label for="uppercase">Incluir letras maiúsculas</label>
      <br>
      <input type="checkbox" id="lowercase" checked>
      <label for="lowercase">Incluir letras minúsculas</label>
      <br>
      <input type="checkbox" id="numbers" checked>
      <label for="numbers">Incluir números</label>
      <br>
      <input type="checkbox" id="symbols" checked>
      <label for="symbols">Incluir símbolos</label>
      <br><br>
      <button type="button" onclick="generatePassword()">Gerar Senha</button>
    </form>
    <div id="password"></div>
  </div>

  <script>
    function generatePassword() {
      var length = document.getElementById("length").value;
      var charset = "";
      if (document.getElementById("uppercase").checked) {
        charset += "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
      }
      if (document.getElementById("lowercase").checked) {
        charset += "abcdefghijklmnopqrstuvwxyz";
      }
      if (document.getElementById("numbers").checked) {
        charset += "0123456789";
      }
      if (document.getElementById("symbols").checked) {
        charset += "!@#$%^&*()_+~`|}{[]:;?><,./-=";
      }
      var password = "";
      for (var i = 0; i < length; ++i) {
        password += charset.charAt(Math.floor(Math.random() * charset.length));
      }
      document.getElementById("password").textContent = password;
    }
  </script>
</body>

</html>
