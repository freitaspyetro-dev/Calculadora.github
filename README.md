
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Calculadora de Probabilidade</title>
    <style>
        body { font-family: Arial, sans-serif; background-color: #f4f4f9; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; }
        .card { background: white; padding: 20px; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); width: 300px; }
        input, button { width: 100%; margin-top: 10px; padding: 8px; box-sizing: border-box; }
        button { background-color: #007bff; color: white; border: none; border-radius: 4px; cursor: pointer; }
        button:hover { background-color: #0056b3; }
        #resultado { margin-top: 15px; font-weight: bold; }
    </style>
</head>
<body>

<div class="card">
    <h3>Calculadora de Probabilidade</h3>
    <label>Casos favoráveis:</label>
    <input type="number" id="favoraveis">
    
    <label>Casos possíveis:</label>
    <input type="number" id="possiveis">
    
    <button onclick="calcular()">Calcular</button>
    
    <div id="resultado"></div>
</div>

<script>
    function calcular() {
        let fav = Number(document.getElementById('favoraveis').value);
        let pos = Number(document.getElementById('possiveis').value);
        let res = document.getElementById('resultado');

        if (pos <= 0) {
            res.style.color = "red";
            res.innerText = "Erro: O número de casos possíveis deve ser maior que zero.";
        } else if (fav < 0) {
            res.style.color = "red";
            res.innerText = "Erro: Os casos favoráveis não podem ser negativos.";
        } else if (fav > pos) {
            res.style.color = "orange";
            res.innerText = "Aviso: Casos favoráveis maiores que os possíveis.";
        } else {
            let prob = (fav / pos) * 100;
            res.style.color = "green";
            res.innerText = `A probabilidade é: ${prob.toFixed(2)}%`;
        }
    }
</script>

</body>
</html>

