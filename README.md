# React-Calculator

## Introduction

The **React-Calculator** is a simple and efficient calculator application built using React. It provides basic arithmetic operations including addition, subtraction, multiplication, and division. This project is an excellent example of a functional React component utilizing hooks such as `useState` and `useRef`.

## Features

- **Addition**: Add two numbers.
- **Subtraction**: Subtract one number from another.
- **Multiplication**: Multiply two numbers.
- **Division**: Divide one number by another.
- **Reset Input**: Clear the input field.
- **Reset Result**: Reset the result to zero.

## Built With

- [React](https://reactjs.org/) - A JavaScript library for building user interfaces.
- [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) - The programming language used.
- [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) - Used for styling the application.


## Installation

To get started with the React-Calculator, follow these steps:

1. **Clone the repository:**
```bash
git clone https://github.com/your-username/React-Calculator.git
```
2. Navigate to the project directory:
```bash
cd React-Calculator
```
3. Install the dependencies:
```bash
npm install
```
4. Start the application:
```bash
npm start
```
## Usage

1. Open your browser and navigate to `http://localhost:3000` to view the calculator.
2. Enter a number in the input field.
3. Click the desired operation button (add, subtract, multiply, divide).
4. The result will be displayed above the input field.
5. Use the "reset input" button to clear the input field and the "reset result" button to reset the result to zero.

## Code Overview

The main functionality of the calculator is implemented in the `App` component located in `App.js`.

### Hooks

- **useState**: Manages the state of the result.
- **useRef**: References the input field and result display.

### Functions

- **plus**: Adds the input value to the current result.
- **minus**: Subtracts the input value from the current result.
- **times**: Multiplies the current result by the input value.
- **divide**: Divides the current result by the input value.
- **resetInput**: Clears the input field.
- **resetResult**: Resets the result to zero.

### Example Code Snippet

```jsx
function App() { 
  const inputRef = useRef(null); 
  const resultRef = useRef(null); 
  const [result, setResult] = useState(0); 
 
  function plus(e) { 
    e.preventDefault(); 
    setResult((result) => result + Number(inputRef.current.value)); 
  }; 
 
  function minus(e) {
    e.preventDefault();
    const inputValue = Number(inputRef.current.value);
    setResult(prevResult => prevResult - inputValue);
  }
  
  function times(e) {
    e.preventDefault();
    const inputValue = Number(inputRef.current.value);
    setResult(prevResult => prevResult * inputValue);
  }
  
  function divide(e) {
    e.preventDefault();
    const inputValue = Number(inputRef.current.value);
    setResult(prevResult => prevResult / inputValue);
  }
  
  function resetInput(e) {
    e.preventDefault();
    inputRef.current.value = '0';
  }
  
  function resetResult(e) {
    e.preventDefault();
    setResult(0);
  }
  
  return ( 
    <div className="App"> 
      <div> 
        <h1>Simplest Working Calculator</h1> 
      </div> 
      <form> 
        <p ref={resultRef}> 
          {result} 
        </p> 
        <input
          pattern="[0-9]" 
          ref={inputRef} 
          type="number" 
          placeholder="Type a number" 
        /> 
        <button onClick={plus}>add</button>
        <button onClick={minus}>subtract</button>
        <button onClick={times}>multiply</button>
        <button onClick={divide}>divide</button>
        <button onClick={resetInput}>reset input</button>
        <button onClick={resetResult}>reset result</button>
      </form> 
    </div> 
  ); 
} 

export default App; 
```
### License
MIT License

Copyright (c) 2024 Benjamin Anderson

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.