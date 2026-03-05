<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Menu-Driven Calculator</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #ffe3ee;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .calculator-container {
            background-color: #abafeb;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            width: 300px;
            text-align: center;
        }

        h2 {
            color: #333;
            margin-bottom: 20px;
        }

        .input-group {
            margin-bottom: 15px;
            text-align: left;
        }

        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            color: #555;
        }

        input, select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            box-sizing: border-box; /* Ensures padding doesn't affect width */
            font-size: 16px;
        }

        button {
            width: 100%;
            padding: 12px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
            transition: background-color 0.3s;
            margin-top: 10px;
        }

        button:hover {
            background-color: #0056b3;
        }

        #result {
            margin-top: 20px;
            padding: 15px;
            background-color: #e9ecef;
            border-radius: 5px;
            font-size: 18px;
            font-weight: bold;
            color: #333;
            min-height: 24px;
        }
    </style>
</head>
<body>

    <div class="calculator-container">
        <h2>Calculator</h2>

        <div class="input-group">
            <label for="num1">Enter First Number:</label>
            <input type="number" id="num1" placeholder="e.g. 10">
        </div>

        <div class="input-group">
            <label for="num2">Enter Second Number:</label>
            <input type="number" id="num2" placeholder="e.g. 5">
        </div>

        <div class="input-group">
            <label for="operation">Select Operation:</label>
            <select id="operation">
                <option value="add">Addition (+)</option>
                <option value="subtract">Subtraction (-)</option>
                <option value="multiply">Multiplication (*)</option>
                <option value="divide">Division (/)</option>
            </select>
        </div>

        <button onclick="calculateResult()">Calculate</button>

        <div id="result">Result will appear here</div>
    </div>

    <script>
        

        function add(a, b) {
            return a + b;
        }

        function subtract(a, b) {
            return a - b;
        }

        function multiply(a, b) {
            return a * b;
        }

        function divide(a, b) {
            if (b === 0) {
                return "Error: Division by zero";
            }
            return a / b;
        }

        
        function calculateResult() {
            const num1Input = document.getElementById('num1').value;
            const num2Input = document.getElementById('num2').value;
            const operation = document.getElementById('operation').value;
            const resultDisplay = document.getElementById('result');

            if (num1Input === "" || num2Input === "") {
                resultDisplay.style.color = "red";
                resultDisplay.innerText = "Please enter both numbers.";
                return;
            }

            const num1 = parseFloat(num1Input);
            const num2 = parseFloat(num2Input);

            let finalResult;

    
            switch (operation) {
                case 'add':
                    finalResult = add(num1, num2);
                    break;
                case 'subtract':
                    finalResult = subtract(num1, num2);
                    break;
                case 'multiply':
                    finalResult = multiply(num1, num2);
                    break;
                case 'divide':
                    finalResult = divide(num1, num2);
                    break;
                default:
                    finalResult = "Invalid Operation";
            }

            resultDisplay.style.color = "#333";
            resultDisplay.innerText = finalResult;
        }
    </script>

</body>
</html>
