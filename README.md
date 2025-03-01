<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Captura de IP com JavaScript</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        .ip-info {
            background-color: #f1f1f1;
            padding: 20px;
            border-radius: 5px;
            display: inline-block;
        }
    </style>
</head>
<body>
    <div class="ip-info">
        <h3>Seu IP é:</h3>
        <p id="ip-address">Carregando...</p>
    </div>

    <script>
        // Fazendo uma requisição para a API ipinfo.io
        fetch('https://ipinfo.io/json?token=7cc710000b0d35')
            .then(response => response.json())
            .then(data => {
                // Exibindo o IP na página
                document.getElementById('ip-address').textContent = data.ip;
            })
            .catch(error => {
                // Caso haja erro na requisição
                document.getElementById('ip-address').textContent = 'Não foi possível obter o IP';
            });
    </script>
</body>
</html>
