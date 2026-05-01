<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Scientific Calculator</title>

<style>
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: #121212;
    font-family: Arial;
}

.calculator {
    background: #1e1e2f;
    padding: 20px;
    border-radius: 15px;
    width: 340px;
}

#display {
    width: 100%;
    height: 60px;
    font-size: 24px;
    margin-bottom: 10px;
    text-align: right;
    padding: 10px;
    border-radius: 10px;
    border: none;
    color: white;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 8px;
}

button {
    height: 55px;
    font-size: 16px;
    border: none;
    border-radius: 8px;
    background: #333;
    color: white;
    cursor: pointer;
}

button:hover {
    background: #555;
}

.equal {
    background: orange;
}

.toggle {
    background: teal;
}
</style>
</head>

<body>

<div class="calculator">
    <input type="text" id="display" disabled>

    <div class="buttons">
        <button onclick="clearDisplay()">C</button>
        <button onclick="append('(')">(</button>
        <button onclick="append(')')">)</button>
        <button onclick="append('/')">÷</button>
        <button onclick="append('*')">×</button>

        <button onclick="append('7')">7</button>
        <button onclick="append('8')">8</button>
        <button onclick="append('9')">9</button>
        <button onclick="append('-')">-</button>
        <button onclick="append('+')">+</button>

        <button onclick="append('4')">4</button>
        <button onclick="append('5')">5</button>
        <button onclick="append('6')">6</button>
        <button onclick="power()">x²</button>
        <button onclick="sqrt()">√</button>

        <button onclick="append('1')">1</button>
        <button onclick="append('2')">2</button>
        <button onclick="append('3')">3</button>
        <button onclick="append('0')">0</button>
        <button onclick="append('.')">.</button>

        <button onclick="sin()">sin</button>
        <button onclick="cos()">cos</button>
        <button onclick="tan()">tan</button>
        <button onclick="log()">log</button>
        <button onclick="ln()">ln</button>

        <button onclick="append(Math.PI)">π</button>
        <button onclick="append(Math.E)">e</button>
        <button onclick="toggleMode()" class="toggle">DEG</button>
        <button onclick="calculate()" class="equal">=</button>
    </div>
</div>

<script>
let isDegree = true;

function append(value) {
    document.getElementById("display").value += value;
}

function clearDisplay() {
    document.getElementById("display").value = "";
}

function calculate() {
    try {
        let result = eval(document.getElementById("display").value);
        document.getElementById("display").value = result;
    } catch {
        alert("Invalid Expression");
    }
}

function toRadians(value) {
    return isDegree ? value * Math.PI / 180 : value;
}

function sin() {
    let val = eval(display.value);
    display.value = Math.sin(toRadians(val));
}

function cos() {
    let val = eval(display.value);
    display.value = Math.cos(toRadians(val));
}

function tan() {
    let val = eval(display.value);
    display.value = Math.tan(toRadians(val));
}

function log() {
    let val = eval(display.value);
    display.value = Math.log10(val);
}

function ln() {
    let val = eval(display.value);
    display.value = Math.log(val);
}

function sqrt() {
    let val = eval(display.value);
    display.value = Math.sqrt(val);
}

function power() {
    let val = eval(display.value);
    display.value = Math.pow(val, 2);
}

function toggleMode() {
    isDegree = !isDegree;
    event.target.innerText = isDegree ? "DEG" : "RAD";
}
</script>

</body>
</html>
