<!doctype html>
<html lang="pt">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Teste de QI — 25 Perguntas</title>
  <style>
    body {
      font-family: system-ui, sans-serif;
      max-width: 900px;
      margin: 40px auto;
      line-height: 1.5;
      background: #fafafa;
      color: #222;
    }
    h1 {
      text-align: center;
      margin-bottom: 20px;
    }
    .q {
      background: white;
      padding: 15px;
      margin: 10px 0;
      border-radius: 10px;
      box-shadow: 0 0 3px rgba(0,0,0,0.1);
    }
    button {
      display: block;
      margin: 20px auto;
      padding: 10px 20px;
      font-size: 16px;
      border: none;
      border-radius: 8px;
      background: #007bff;
      color: white;
      cursor: pointer;
    }
    #resultado {
      display: none;
      background: #e8f5e9;
      padding: 20px;
      border-radius: 10px;
      text-align: center;
    }
  </style>
</head>
<body>

  <h1>Teste de QI — 25 Perguntas</h1>
  <p>Responda às 25 perguntas abaixo e clique em <strong>Ver Resultado</strong> no final para saber sua pontuação.</p>

  <form id="quizForm">
    <!-- Exemplo de perguntas (as mesmas 25 básicas de raciocínio lógico) -->
    <div class="q">
      <strong>1.</strong> Se todas as rosas são flores e algumas flores murcham, então:
      <br>
      <label><input type="radio" name="q1" value="0"> Nem todas as rosas murcham</label><br>
      <label><input type="radio" name="q1" value="1"> Algumas rosas podem murchar</label><br>
      <label><input type="radio" name="q1" value="0"> Todas as rosas murcham</label>
    </div>

    <div class="q">
      <strong>2.</strong> Sequência: 2, 4, 8, 16, ?<br>
      <label><input type="radio" name="q2" value="1"> 32</label><br>
      <label><input type="radio" name="q2" value="0"> 24</label>
    </div>

    <div class="q">
      <strong>3.</strong> Qual destes não pertence ao grupo: maçã, pêra, banana, cebola?<br>
      <label><input type="radio" name="q3" value="1"> Cebola</label><br>
      <label><input type="radio" name="q3" value="0"> Banana</label>
    </div>

    <!-- ... (adicione as restantes perguntas semelhantes até a nº25) ... -->

    <button type="button" onclick="verResultado()">Ver Resultado</button>
  </form>

  <div id="resultado">
    <h2>Seu Resultado</h2>
    <p id="pontuacao"></p>
    <p id="interpretacao"></p>
  </div>

  <script>
    function verResultado() {
      const form = document.getElementById('quizForm');
      let total = 0;
      const inputs = form.querySelectorAll('input[type=radio]:checked');
      inputs.forEach(i => total += parseInt(i.value));

      document.getElementById('pontuacao').textContent = `Pontuação: ${total} / 25`;

      let nivel = '';
      if (total >= 22) nivel = '🧠 Muito acima da média';
      else if (total >= 18) nivel = '👍 Acima da média';
      else if (total >= 13) nivel = '🙂 Média';
      else if (total >= 9) nivel = '😕 Abaixo da média';
      else nivel = '😬 Muito abaixo da média';

      document.getElementById('interpretacao').textContent = nivel;
      document.getElementById('resultado').style.display = 'block';
      window.scrollTo(0, document.body.scrollHeight);
    }
  </script>

</body>
</html>
