# Advanced-Calculator
<!DOCTYPE html>
<html>
<head>
<title>Advanced Calculator</title>
<style>
body {
  font-family: sans-serif;
}
.calculator {
  width: 300px;
  margin: 50px auto;
  border: 1px solid #ccc;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 2px 2px 5px #888888;
}
.display {
  background-color: #eee;
  padding: 10px;
  margin-bottom: 10px;
  text-align: right;
  font-size: 1.5em;
  border-radius: 5px;
}
button {
  width: 60px;
  height: 40px;
  margin: 5px;
  border-radius: 5px;
  font-size: 1.2em;
  border: none;
  background-color: #f0f0f0;
  cursor: pointer;
}
button:hover {
  background-color: #ddd;
}
.operator {
  background-color: #ffb347;
}
.operator:hover {
  background-color: #ffa000;
}
</style>
</head>
<body>
<div class="calculator">
  <div class="display" id="display">0</div>
  <button onclick="clearDisplay()">C</button>
  <button onclick="appendToDisplay('7')">7</button>
  <button onclick="appendToDisplay('8')">8</button>
  <button onclick="appendToDisplay('9')">9</button>
  <button class="operator" onclick="appendToDisplay('/')">/</button>
  <button onclick="appendToDisplay('4')">4</button>
  <button onclick="appendToDisplay('5')">5</button>
  <button onclick="appendToDisplay('6')">6</button>
  <button class="operator" onclick="appendToDisplay('*')">*</button>
  <button onclick="appendToDisplay('1')">1</button>
  <button onclick="appendToDisplay('2')">2</button>
  <button onclick="appendToDisplay('3')">3</button>
  <button class="operator" onclick="appendToDisplay('-')">-</button>
  <button onclick="appendToDisplay('0')">0</button>
  <button onclick="appendToDisplay('.')">.</button>
  <button onclick="calculate()">=</button>
  <button class="operator" onclick="appendToDisplay('+')">+</button>
  <button onclick="sqrt()">√</button>
  <button onclick="power()">x²</button>
  <button onclick="percent()">%</button>
</div>

<script>
let display = document.getElementById('display');

function appendToDisplay(value) {
  if (display.textContent === '0' && !isNaN(value)) {
    display.textContent = value;
  } else {
    display.textContent += value;
  }
}

function clearDisplay() {
  display.textContent = '0';
}

function calculate() {
  try {
    display.textContent = eval(display.textContent);
  } catch (error) {
    display.textContent = 'Error';
  }
}

function sqrt() {
  display.textContent = Math.sqrt(parseFloat(display.textContent));
}

function power() {
  display.textContent = Math.pow(parseFloat(display.textContent), 2);
}

function percent() {
  display.textContent = parseFloat(display.textContent) / 100;
}
</script>

</body>
</html>
