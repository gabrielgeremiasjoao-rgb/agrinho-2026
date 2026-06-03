# agrinho-2026
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rotação de Culturas - Agro Forte e Futuro Sustentável</title>
    <style>
        /* Estilos Gerais */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f4f9f4;
            color: #333;
            line-height: 1.6;
        }

        /* Cabeçalho */
        header {
            background-color: #2e7d32;
            color: white;
            padding: 30px 0;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }

        header h1 {
            font-size: 2.3rem;
            margin-bottom: 5px;
        }

        header p {
            font-style: italic;
            font-size: 1.1rem;
            color: #e8f5e9;
        }

        /* Container Principal */
        .container {
            max-width: 800px;
            margin: 40px auto;
            padding: 0 20px;
        }

        /* Seções */
        section {
            background: white;
            padding: 30px;
            margin-bottom: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }

        h2 {
            color: #2e7d32;
            border-bottom: 2px solid #81c784;
            padding-bottom: 10px;
            margin-bottom: 20px;
        }

        /* Formulário e Seleção */
        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            font-weight: bold;
            margin-bottom: 8px;
            color: #1b5e20;
        }

        select {
            width: 100%;
            padding: 12px;
            border: 2px solid #a5d6a7;
            border-radius: 6px;
            font-size: 1rem;
            background-color: #fafafa;
            outline: none;
            transition: border-color 0.3s;
        }

        select:focus {
            border-color: #2e7d32;
        }

        button {
            background-color: #2e7d32;
            color: white;
            border: none;
            padding: 12px 20px;
            font-size: 1rem;
            font-weight: bold;
            border-radius: 6px;
            cursor: pointer;
            width: 100%;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: #1b5e20;
        }

        /* Painel de Resultado */
        .resultado-box {
            margin-top: 25px;
            padding: 20px;
            background-color: #e8f5e9;
            border-left: 6px solid #2e7d32;
            border-radius: 4px;
            display: none;
        }

        .resultado-box h3 {
            color: #1b5e20;
            margin-bottom: 10px;
        }

        /* Rodapé */
        footer {
            background-color: #232323;
            color: #ccc;
            text-align: center;
            padding: 20px 0;
            margin-top: 50px;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

    <header>
        <h1>Simulador de Rotação de Culturas</h1>
        <p>Agro Forte e Futuro Sustentável</p>
    </header>

    <div class="container">

        <section id="conceito">
            <h2>O que é Rotação de Culturas?</h2>
            <p>A rotação de culturas é uma prática agrícola sustentável que consiste em alternar, de forma planejada, diferentes espécies de plantas em uma mesma área. Isso melhora as propriedades físicas e biológicas do solo, ajuda no controle de pragas e doenças, e reduz a dependência de fertilizantes químicos.</p>
        </section>

        <section id="simulador">
            <h2>Planeje sua Próxima Safra</h2>
            <p style="margin-bottom: 15px;">Selecione o que você plantou na última safra para descobrir qual é a melhor opção de rotação para manter o solo forte:</p>
            
            <div class="form-group">
                <label for="culturaAtual">Cultura plantada recentemente:</label>
                <select id="culturaAtual">
                    <option value="">-- Escolha uma opção --</option>
                    <option value="soja">Soja (Leguminosa)</option>
                    <option value="milho">Milho (Gramínea)</option>
                    <option value="trigo">Trigo / Aveia (Cereal de Inverno)</option>
                    <option value="pastagem">Brachiaria / Pastagem (Recuperação)</option>
                </select>
            </div>

            <button onclick="calcularRotacao()">Recomendar Próxima Cultura</button>

            <div id="resultado" class="resultado-box">
                <h3 id="proximaCultura"></h3>
                <p id="justificativa"></p>
            </div>
        </section>

    </div>

    <footer>
        <p>&copy; 2026 Projeto Agrinho - Agro Forte e Futuro Sustentável.</p>
        <p>Desenvolvido por: <strong>João Gabriel Geremias</strong></p>
    </footer>

    <script>
        function calcularRotacao() {
            const cultura = document.getElementById('culturaAtual').value;
            const resultadoBox = document.getElementById('resultado');
            const proximaCulturaTag = document.getElementById('proximaCultura');
            const justificativaTag = document.getElementById('justificativa');

            if (cultura === "") {
                alert("Por favor, selecione uma cultura atual.");
                resultadoBox.style.display = "none";
                return;
            }

            let recomendacao = "";
            let explicacao = "";

            switch(cultura) {
                case 'soja':
                    recomendacao = "🌽 Próximo Plantio Recomendado: Milho ou Gramíneas";
                    explicacao = "A soja é uma leguminosa que fixa nitrogênio no solo. Plantar milho em seguida aproveita esse nutriente naturalmente, gerando uma palhada rica que protege a terra contra a erosão e quebra o ciclo de pragas.";
                    break;
                case 'milho':
                    recomendacao = "🌱 Próximo Plantio Recomendado: Plantas de Cobertura ou Trigo (Inverno)";
                    explicacao = "O milho consome bastante nitrogênio. O ideal é entrar com uma cultura de inverno ou leguminosas de cobertura para repor a matéria orgânica e descansar o solo antes da próxima grande safra.";
                    break;
                case 'trigo':
                    recomendacao = "🌿 Próximo Plantio Recomendado: Soja";
                    explicacao = "A palha do trigo deixa o solo com excelente proteção térmica e controle de umidade. A soja se desenvolve muito bem nessa cobertura, garantindo uma safra mais forte e rentável.";
                    break;
                case 'pastagem':
                    recomendacao = "🚜 Próximo Plantio Recomendado: Soja (Integração Lavoura-Pecuária)";
                    explicacao = "A pastagem estruturou o solo física e biologicamente. Entrar com a soja agora limpa o campo de pragas da pastagem e aproveita a terra descompactada pelas raízes profundas do capim.";
                    break;
            }

            proximaCulturaTag.innerText = recomendacao;
            justificativaTag.innerText = explicacao;
            resultadoBox.style.display = "block";
        }
    </script>
</body>
</html>
