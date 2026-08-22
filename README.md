# Ex04 Simple Calculator - React Project
## Date:22-03-2026
## Name : S DURGESH
## Reg No :212225230064

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
Calculator.js
```import React, { useState } from 'react';
import './Calculator.css';

function Calculator() {
  const [input, setInput] = useState('');

  const handleClick = (value) => {
    setInput(input + value);
  };

  const handleClear = () => {
    setInput('');
  };

  const handleEqual = () => {
    try {
      setInput(eval(input).toString());
    } catch (error) {
      setInput('Error');
    }
  };

  const buttons = [
    '7', '8', '9', '/',
    '4', '5', '6', '*',
    '1', '2', '3', '-',
    '0', '.', '=', '+'
  ];

  return (
    <div className="calculator">
      <input type="text" className="screen" value={input} readOnly />
      <div className="buttons">
        <button className="btn clear" onClick={handleClear}>C</button>
        {buttons.map((btn, index) => (
          <button
            key={index}
            className="btn"
            onClick={() =>
              btn === '=' ? handleEqual() : handleClick(btn)
            }
          >
            {btn}
          </button>
        ))}
      </div>
    </div>
  );
}

export default Calculator;
```
Calculator.css
```
body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  background: linear-gradient(135deg, #667eea, #764ba2);
  font-family: Arial, sans-serif;
}

.calculator {
  background: #222;
  padding: 20px;
  border-radius: 15px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
  width: 300px;
}

.screen {
  width: 100%;
  height: 50px;
  font-size: 24px;
  text-align: right;
  margin-bottom: 15px;
  padding: 10px;
  border-radius: 8px;
  border: none;
  background: #111;
  color: #fff;
  box-sizing: border-box;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

.btn {
  padding: 15px;
  font-size: 18px;
  border: none;
  border-radius: 8px;
  background: #333;
  color: #fff;
  cursor: pointer;
  transition: 0.2s;
}

.btn:hover {
  background: #ff9500;
  color: #000;
}

.clear {
  grid-column: span 4;
  background: #e74c3c;
}

.clear:hover {
  background: #c0392b;
}

@media (max-width: 400px) {
  .calculator {
    width: 90%;
  }
}
```
src/App.js
```
import React from 'react';
import Calculator from './Calculator';
import './Calculator.css';

function App() {
  return (
    <div className="App">
      <Calculator />
    </div>
  );
}

export default App;
```



## OUTPUT
<img width="1915" height="904" alt="image" src="https://github.com/user-attachments/assets/c69c00fd-0ee4-4905-bb51-94793f140286" />



## RESULT
The program for developing a simple calculator in React.js is executed successfully.
