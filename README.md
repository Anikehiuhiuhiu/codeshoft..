# codeshoft..
calculator 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: grid;
            place-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f4;
        }

        #calculator {
            border: 2px solid #ccc;
            border-radius: 5px;
            overflow: hidden;
            width: 300px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        #display {
            height: 50px;
            font-size: 1.5em;
            text-align: right;
            padding: 0 10px;
            background: #fff;
        }

        button {
            width: 25%;
            height: 50px;
            font-size: 1.2em;
            border: none;
            outline: none;
            cursor: pointer;
        }

        button.operator {
            background: #f2184f;
            color: #fff;
        }

        button.double {
            width: 50%;
        }

        button.equal {
            background: #28a745;
            color: #fff;
        }
    </style>
</head>
<body>

    <div id="calculator">
        <div id="display"></div>
        <button onclick="clearDisplay()">C</button>
        <button onclick="appendInput('/')" class="operator">/</button>
        <button onclick="appendInput('*')" class="operator">*</button>
        <button onclick="appendInput('7')">7</button>
        <button onclick="appendInput('8')">8</button>
        <button onclick="appendInput('9')">9</button>
        <button onclick="appendInput('-')" class="operator">-</button>
        <button onclick="appendInput('4')">4</button>
        <button onclick="appendInput('5')">5</button>
        <button onclick="appendInput('6')">6</button>
        <button onclick="appendInput('+')" class="operator">+</button>
        <button onclick="appendInput('1')">1</button>
        <button onclick="appendInput('2')">2</button>
        <button onclick="appendInput('3')">3</button>
        <button onclick="calculate()" class="double equal">=</button>
        <button onclick="appendInput('0')">0</button>
        <button onclick="appendInput('.')">.</button>
    </div>

    <script>
        let display = document.getElementById('display');
        let input = '';

        function appendInput(value) {
            input += value;
            updateDisplay();
        }

        function clearDisplay() {
            input = '';
            updateDisplay();
        }

        function calculate() {
            try {
                input = eval(input).toString();
                updateDisplay();
            } catch (error) {
                display.textContent = 'Error';
            }
        }

        function updateDisplay() {
            display.textContent = input;
        }
    </script>

</body>
</html>

