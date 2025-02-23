<!DOCTYPE html>
<html lang="pt-BR">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Gerador de Runs - Pokémon Infinite Fusion</title>  
    <style>  
        body {  
            font-family: Arial, sans-serif;  
            text-align: center;  
            background-color: #f8f9fa;  
            padding: 20px;  
        }  
        h1 {  
            color: #333;  
        }  
        button, select {  
            padding: 10px;  
            font-size: 16px;  
            margin-top: 10px;  
            cursor: pointer;  
        }  
        button {  
            background-color: #007bff;  
            color: white;  
            border: none;  
            border-radius: 5px;  
        }  
        button:hover {  
            background-color: #0056b3;  
        }  
        #resultado {  
            margin-top: 20px;  
            font-size: 18px;  
            color: #333;  
        }  
        img {  
            margin-top: 20px;  
            max-width: 100%;  
            height: auto;  
            border-radius: 10px;  
        }  
    </style>  
</head>  
<body>  
    <h1>Gerador de Runs - Pokémon Infinite Fusion</h1>  

    <label for="escolha">Escolha o tipo de run ou deixe aleatório:</label>  
    <select id="escolha">  
        <option value="random">Aleatório</option>  
        <option value="Monotype">Monotype</option>  
        <option value="Cor específica">Cor específica</option>  
        <option value="Fusão com Pokémon específico">Fusão com Pokémon específico</option>  
        <option value="Solo Run">Solo Run</option>  
        <option value="Mono Legendary">Mono Legendary</option>  
    </select>  

    <button onclick="gerarRun()">Gerar Run</button>  
    <div id="resultado"></div>  

<script>  
    function gerarRun() {  
        const tiposDePokemon = ["Monotype", "Cor específica", "Fusão com Pokémon específico", "Solo Run", "Mono Legendary"];  
        const tiposPossiveis = ["Fogo", "Água", "Planta", "Elétrico", "Gelo", "Lutador", "Fantasma", "Venenoso", "Terrestre",   
                                "Normal", "Psíquico", "Inseto", "Pedra", "Dragão", "Sombrio", "Metálico", "Fada"];  
        const coresPossiveis = ["Vermelho", "Azul", "Amarelo", "Verde", "Roxo", "Cinza", "Branco", "Preto",   
                                "Dourado", "Prata", "Bege", "Rosa", "Marrom"];  

        let escolhaUsuario = document.getElementById("escolha").value;  
        let tipoSelecionado = escolhaUsuario === "random" ? tiposDePokemon[Math.floor(Math.random() * tiposDePokemon.length)] : escolhaUsuario;  
        let detalhe = "";  

        if (tipoSelecionado === "Monotype") {  
            detalhe = tiposPossiveis[Math.floor(Math.random() * tiposPossiveis.length)];  
        } else if (tipoSelecionado === "Cor específica") {  
            detalhe = coresPossiveis[Math.floor(Math.random() * coresPossiveis.length)];  
        } else if (tipoSelecionado === "Fusão com Pokémon específico" || tipoSelecionado === "Solo Run") {  
            detalhe = `National Dex #${String(Math.floor(Math.random() * 1015) + 1).padStart(3, '0')}`;  
        } else if (tipoSelecionado === "Mono Legendary") {  
            detalhe = "Use apenas Pokémon lendários.";  
        }  

        document.getElementById("resultado").innerHTML = `  
            <p><strong>Tipo de Run:</strong> ${tipoSelecionado}</p>  
            <p><strong>Detalhe:</strong> ${detalhe}</p>  
        `;  
    }  
</script>

</body>  
</html>
