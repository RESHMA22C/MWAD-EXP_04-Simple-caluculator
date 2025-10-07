# MWAD-EXP_04-Simple-caluculator
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
# index.html
~~~

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Black & White Calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="calculator">
        <div class="display">
            <input type="text" id="result" readonly placeholder="0">
        </div>
        <div class="buttons">
            <button onclick="clearDisplay()" class="span-two">C</button>
            <button onclick="deleteLast()">DEL</button>
            <button onclick="appendOperator('/')">÷</button>

            <button onclick="appendNumber('7')">7</button>
            <button onclick="appendNumber('8')">8</button>
            <button onclick="appendNumber('9')">9</button>
            <button onclick="appendOperator('*')">×</button>

            <button onclick="appendNumber('4')">4</button>
            <button onclick="appendNumber('5')">5</button>
            <button onclick="appendNumber('6')">6</button>
            <button onclick="appendOperator('-')">-</button>

            <button onclick="appendNumber('1')">1</button>
            <button onclick="appendNumber('2')">2</button>
            <button onclick="appendNumber('3')">3</button>
            <button onclick="appendOperator('+')">+</button>

            <button onclick="appendNumber('0')" class="span-two">0</button>
            <button onclick="appendNumber('.')">.</button>
            <button onclick="calculate()">=</button>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>
~~~

# style.css
~~~
**body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #ffffff; /* White background */
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.calculator {
    background-color: #f0f0f0; /* Light gray calculator body */
    border-radius: 15px;
    box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    padding: 20px;
}

.display input {
    width: 100%;
    height: 60px;
    text-align: right;
    font-size: 2rem;
    padding: 10px;
    border: 2px solid #ccc;
    border-radius: 10px;
    margin-bottom: 20px;
    background-color: #ffffff; /* White display */
    color: #000000; /* Black text */
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 70px);
    grid-gap: 10px;
}

button {
    padding: 20px;
    font-size: 1.5rem;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    transition: all 0.2s;
    background-color: #000000; /* Black buttons */
    color: #ffffff; /* White text */
    box-shadow: 0 5px #555555; /* Dark gray shadow */
}

button:hover {
    background-color: #333333; /* Slightly lighter black on hover */
}

button:active {
    transform: translateY(2px);
    box-shadow: 0 3px #555555;
}

.span-two {
    grid-column: span 2;
}

~~~

# script.js
~~~
const resultInput = document.getElementById('result');

function appendNumber(number) {
    if(resultInput.value === "0" && number !== ".") {
        resultInput.value = number;
    } else {
        resultInput.value += number;
    }
}

function appendOperator(operator) {
    const lastChar = resultInput.value.slice(-1);
    if(["+", "-", "*", "/"].includes(lastChar)) {
        resultInput.value = resultInput.value.slice(0, -1) + operator;
    } else {
        resultInput.value += operator;
    }
}

function clearDisplay() {
    resultInput.value = "";
}

function deleteLast() {
    resultInput.value = resultInput.value.slice(0, -1);
}

function calculate() {
    try {
        resultInput.value = eval(resultInput.value);
    } catch (e) {
        alert("Invalid Expression");
    }
}


~~~
## OUTPUT

 <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/07dc8ff7-8a33-4548-b106-d5d8f54d69aa" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
