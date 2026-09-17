# Ex04 Simple Calculator - React Project
## Date:18-08-2026
## Name :MIRTYUNJAY S 
## Reg No :212224040190

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
CSS
```
body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: linear-gradient(135deg, #6a11cb, #2575fc);
  margin: 0;
  font-family: Arial, sans-serif;
}

.calculator {
  background: rgba(255, 255, 255, 0.1);
  padding: 20px;
  border-radius: 15px;
  box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.3);
  text-align: center;
  width: 320px;
  backdrop-filter: blur(10px);
}

h1 {
  margin: 10px 0;
  font-size: 28px;
  font-weight: bold;
  color: #fff;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
}

.display {
  background-color: #000;
  color: #0f0;
  width: 100%;
  height: 60px;
  text-align: right;
  font-size: 24px;
  border-radius: 10px;
  padding: 10px;
  box-sizing: border-box;
  margin-bottom: 20px;
  font-family: "Courier New", Courier, monospace;
  box-shadow: inset 0px 0px 5px rgba(0, 0, 0, 0.5);
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 15px;
}

button {
  width: 100%;
  height: 60px;
  font-size: 20px;
  border: none;
  border-radius: 10px;
  background: linear-gradient(135deg, #ffffff, #d4d4d4);
  box-shadow: 2px 4px 6px rgba(0, 0, 0, 0.2);
  cursor: pointer;
  transition: all 0.2s ease-in-out;
}

button:hover {
  background: linear-gradient(135deg, #f0f0f0, #c0c0c0);
  transform: translateY(-2px);
}

button:active {
  transform: scale(0.95);
  box-shadow: inset 2px 2px 5px rgba(0, 0, 0, 0.3);
}

.btn-ac {
  background: linear-gradient(135deg, #ff4b4b, #ff0000);
  color: white;
}

.btn-ac:hover {
  background: linear-gradient(135deg, #ff6b6b, #ff3333);
}

.btn-special {
  background: linear-gradient(135deg, #ffa500, #ff7f00);
  color: white;
}

.btn-special:hover {
  background: linear-gradient(135deg, #ffb733, #ff9933);
}

.btn-operator {
  background: linear-gradient(135deg, #4caf50, #388e3c);
  color: white;
}

.btn-operator:hover {
  background: linear-gradient(135deg, #66bb6a, #43a047);
}

.btn-equal {
  background: linear-gradient(135deg, #2196f3, #1976d2);
  color: white;
  grid-column: span 2;
}

.btn-equal:hover {
  background: linear-gradient(135deg, #42a5f5, #1e88e5);
}

.footer {
  margin-top: 20px;
  font-size: 14px;
  color: #fff;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
}

.footer p {
  margin: 5px 0;
}
```
HTML
```
<!DOCTYPE html>
<html>
<head>
<title>Quick Math</title>
<style>
body{text-align:center;font-family:Arial;background:skyblue}
.calculator{width:300px;margin:50px auto;padding:20px;background:#222;border-radius:15px}
#display{background:#111;color:white;font-size:30px;padding:15px;text-align:right;margin-bottom:10px}
button{width:60px;height:55px;margin:4px;border:0;border-radius:8px;font-size:20px}
.num{background:#555;color:white}
.op{background:orange;color:white}
.ac{background:red;color:white}
.eq{background:green;color:white}
footer{color:white;font-size:12px;margin-top:15px}
</style>
</head>

<body>
<div class="calculator">
<h2 style="color:white">Quick Math</h2>
<div id="display">0</div>

<button class="ac" onclick="c('AC')">AC</button>
<button onclick="c('⌫')">⌫</button>
<button class="op" onclick="c('%')">%</button>
<button class="op" onclick="c('/')">/</button><br>

<button class="num" onclick="c('7')">7</button>
<button class="num" onclick="c('8')">8</button>
<button class="num" onclick="c('9')">9</button>
<button class="op" onclick="c('*')">*</button><br>

<button class="num" onclick="c('4')">4</button>
<button class="num" onclick="c('5')">5</button>
<button class="num" onclick="c('6')">6</button>
<button class="op" onclick="c('-')">-</button><br>

<button class="num" onclick="c('1')">1</button>
<button class="num" onclick="c('2')">2</button>
<button class="num" onclick="c('3')">3</button>
<button class="op" onclick="c('+')">+</button><br>

<button class="num" onclick="c('0')">0</button>
<button class="num" onclick="c('.')">.</button>
<button class="eq" onclick="c('=')">=</button>

<footer>
DEVELOPED BY MIRTYUNJAY S <br>
Reg No: 212224040190
</footer>
</div>

<script>
let x="";
function c(v){
if(v=="AC")x="";
else if(v=="⌫")x=x.slice(0,-1);
else if(v=="="){try{x=eval(x)}catch{x="Error"}}
else if(v=="%")x=eval(x)/100;
else x+=v;
document.getElementById("display").innerText=x||"0";
}
</script>
</body>
</html>


```



## OUTPUT
<img width="1920" height="1200" alt="Screenshot 2026-09-17 084435" src="https://github.com/user-attachments/assets/87ef1fa8-2b1a-452a-8a73-3510121e3747" />
<img width="1920" height="1200" alt="Screenshot 2026-09-17 084447" src="https://github.com/user-attachments/assets/2fe4457f-49c8-43cf-982f-4a26c21bf2d7" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
