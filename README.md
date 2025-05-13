# calculatorproject
This is a basic calculator web application built using HTML, CSS, and JavaScript. It allows users to perform simple arithmetic operations such as:  Addition, Subtraction, Multiplication, Division. This project helps in understanding JavaScript functions, event handling, and DOM manipulation.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Calculator</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" disabled />
    <div class="buttons">
      <button onclick="clearDisplay()">C</button>
      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('+')">+</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('-')">-</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('*')">*</button>
      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('/')">/</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('0')">0</button>
      <button onclick="calculate()">=</button>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>
body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f0f0f0;
  font-family: Arial, sans-serif;
}

.calculator {
  background: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px #aaa;
  width: 250px;
}

#display {
  width: 100%;
  padding: 10px;
  margin-bottom: 10px;
  font-size: 20px;
  text-align: right;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  padding: 15px;
  font-size: 18px;
  cursor: pointer;
}
function appendValue(val) {
  document.getElementById("display").value += val;
}

function clearDisplay() {
  document.getElementById("display").value = "";
}

function calculate() {
  try {
    document.getElementById("display").value = eval(
      document.getElementById("display").value
    );
  } catch {
    document.getElementById("display").value = "Error";
  }
}
