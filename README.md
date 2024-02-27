<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f7dada; /* Cor de fundo rosa claro */
        }
        .calculator {
            width: 300px;
            margin: 50px auto;
            border: 2px solid #f78ca0; /* Cor da borda rosa */
            border-radius: 10px;
            background-color: #fce1e1; /* Cor de fundo rosa claro */
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            padding-bottom: 10px; /* Espaçamento inferior */
        }
        input[type="text"] {
            width: calc(100% - 20px); /* Largura ajustada */
            height: 50px;
            font-size: 24px;
            text-align: right;
            border: none;
            border-bottom: 2px solid #f78ca0; /* Cor da borda rosa */
            outline: none;
            background-color: #fce1e1; /* Cor de fundo rosa claro */
            padding: 5px 10px;
            border-radius: 10px 10px 0 0;
        }
        input[type="button"] {
            width: 70px;
            height: 70px;
            margin: 5px;
            font-size: 24px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            background-color: #f78ca0; /* Cor rosa */
            color: white; /* Cor do texto */
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: background-color 0.3s;
        }
        input[type="button"]:hover {
            background-color: #ff6699; /* Cor rosa mais clara ao passar o mouse */
        }
        input[type="button"].operator {
            background-color: #ff6666; /* Cor rosa mais escura para operadores */
        }
        input[type="button"].operator:hover {
            background-color: #ff3333; /* Cor rosa mais clara para operadores ao passar o mouse */
        }
        input[type="button"].equals {
            background-color: #ff8c8c; /* Cor rosa claro para o botão de igual */
        }
        input[type="button"].equals:hover {
            background-color: #ff4d4d; /* Cor rosa mais clara para o botão de igual ao passar o mouse */
        }
        input[type="button"].clear {
            background-color: #ff4d4d; /* Cor rosa para o botão de limpar */
        }
        input[type="button"].clear:hover {
            background-color: #ff1a1a; /* Cor rosa mais clara para o botão de limpar ao passar o mouse */
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" readonly>
        <br>
        <input type="button" value="1" onclick="addToDisplay('1')">
        <input type="button" value="2" onclick="addToDisplay('2')">
        <input type="button" value="3" onclick="addToDisplay('3')">
        <input type="button" value="+" onclick="addToDisplay('+')" class="operator">
        <br>
        <input type="button" value="4" onclick="addToDisplay('4')">
        <input type="button" value="5" onclick="addToDisplay('5')">
        <input type="button" value="6" onclick="addToDisplay('6')">
        <input type="button" value="-" onclick="addToDisplay('-')" class="operator">
        <br>
        <input type="button" value="7" onclick="addToDisplay('7')">
        <input type="button" value="8" onclick="addToDisplay('8')">
        <input type="button" value="9" onclick="addToDisplay('9')">
        <input type="button" value="*" onclick="addToDisplay('*')" class="operator">
        <br>
        <input type="button" value="C" onclick="clearDisplay()" class="clear">
        <input type="button" value="0" onclick="addToDisplay('0')">
        <input type="button" value="=" onclick="calculate()" class="equals">
        <input type="button" value="/" onclick="addToDisplay('/')" class="operator">
        <br>
        <input type="button" value="AND" onclick="addToDisplay(' && ')" class="logical">
        <input type="button" value="OR" onclick="addToDisplay(' || ')" class="logical">
    </div>

    <script>
        function addToDisplay(value) {
            document.getElementById("display").value += value;
        }

        function clearDisplay() {
            document.getElementById("display").value = "";
        }

        function calculate() {
            try {
                var result = eval(document.getElementById("display").value);
                document.getElementById("display").value = result;
            } catch (error) {
                document.getElementById("display").value = "Erro";
            }
        }
    </script>
</body>
</html>


