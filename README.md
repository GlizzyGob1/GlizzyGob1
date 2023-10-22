<!DOCTYPE <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>CALCULATOR</title>
<style>
.calculator {
width: 400px;
background-color: #f2f2f2;
border: 2px solid #ccc;
border-radius: 10px;
margin: 0 auto;
padding: 20px;
}

.fake-screen {
background-color: #000;
color: #fff;
font-size: 24px;
text-align: right;
padding: 10px;
border: 1px solid #ccc;
border-radius: 5px;
margin-bottom: 10px;
}

.question-screen {
background-color: #ddd;
font-size: 18px;
text-align: left;
padding: 10px;
border: 1px solid #ccc;
border-radius: 5px;
margin-bottom: 10px;
}

.button-container {
display: grid;
grid-template-columns: repeat(4, 1fr);
grid-gap: 10px;
}

button {
width: 100%;
padding: 15px;
background-color: #f2f2f2;
border: 1px solid #ccc;
font-size: 20px;
cursor: pointer;
}

button:hover {
background-color: #ddd;
}

.output {
font-weight: bold;
text-align: right;
padding: 10px;
background-color: #ddd;
border: 1px solid #ccc;
border-radius: 5px;
margin-bottom: 10px;
font-size: 24px;
}
</style>
</head>
<body>
<div class="calculator">
<div class="question-screen" id="question">Enter your expression:</div>
<div class="fake-screen" id="result">0</div>
<div class="button-container">
<button onclick="addToInput('7')">7</button>
<button onclick="addToInput('8')">8</button>
<button onclick="addToInput('9')">9</button>
<button onclick="addToInput('/')">÷</button>
<button onclick="addToInput('4')">4</button>
<button onclick="addToInput('5')">5</button>
<button onclick="addToInput('6')">6</button>
<button onclick="addToInput('*')">x</button>
<button onclick="addToInput('1')">1</button>
<button onclick="addToInput('2')">2</button>
<button onclick="addToInput('3')">3</button>
<button onclick="addToInput('-')">-</button>
<button onclick="addToInput('0')">0</button>
<button onclick="addToInput('.')">.</button>
<button onclick="clearInput()">C</button>
<button onclick="addToInput('+')">+</button>
<button onclick="calculate()">=</button>
<button onclick="calculateSin()">sin</button>
<button onclick="calculateCos()">cos</button>
<button onclick="calculateTan()">tan</button>
<button onclick="calculateSqrt()">√</button>
<button onclick="calculateLog()">log</button>
<button onclick="calculateExp()">e^x</button>
<button onclick="calculateFactorial()">!</button>
<button onclick="addToInput('(')">(</button>
<button onclick="addToInput(')')">)</button>
<button onclick="addToInput('%')">%</button>
</div>
</div>

<script>
function addToInput(value) {
var currentValue = document.getElementById("result").innerHTML;
if (currentValue === '0' && value !== '.') {
document.getElementById("result").innerHTML = value;
} else {
document.getElementById("result").innerHTML += value;
}
}

function calculate() {
var expression = document.getElementById("result").innerHTML;
try {
var result = eval(expression);
document.getElementById("result").innerHTML = result.toFixed(4);
document.getElementById("question").innerHTML = "Expression: " + expression;
} catch (error) {
document.getElementById("result").innerHTML = "Error";
document.getElementById("question").innerHTML = "Invalid Expression";
}
}

function clearInput() {
document.getElementById("result").innerHTML = '0';
document.getElementById("question").innerHTML = 'Enter your expression:';
}

// Add your other calculation functions here...

</script>
</body>
</html>

