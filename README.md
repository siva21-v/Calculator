# 🔢 Simple Calculator

A modern and responsive calculator built using **HTML, CSS, and JavaScript**.  
It performs basic arithmetic operations and includes features like **AC**, **DEL**, **percentage**, and more.

---

## 📸 Preview
<img width="1920" height="925" alt="Calculator Screenshot" src="https://github.com/user-attachments/assets/eec3aa51-0951-4ea6-8d74-cafbc81d7338" />

---

## 🛠️ Features

- ✔ Addition, Subtraction, Multiplication, Division  
- ✔ Percentage (%) operation  
- ✔ **AC** → Clear all  
- ✔ **DEL** → Delete last character  
- ✔ Smooth UI with glassmorphism effect  
- ✔ Fully responsive layout  
- ✔ Easy to understand JavaScript logic  

---

## 📂 Project Structure

calculator/
│
├── index.html
├── style.css
└── script.js

pgsql
Copy code

---

## 💻 Technologies Used

- **HTML5**
- **CSS3**
- **JavaScript (ES6)**

---

## 📜 Code Explanation

### 🔹 JavaScript Logic (`script.js`)
- Stores user input in a variable `string`
- Updates display using `input.value`
- Evaluates expression using `eval()` when `=` is pressed
- Deletes last character using `substring()`
- Clears everything using `AC`

```js
let input = document.getElementById('inputBox');
let buttons = document.querySelectorAll('button');

let string = "";
let arr = Array.from(buttons);
arr.forEach(button => {
    button.addEventListener('click', (e) => {
        if(e.target.innerHTML == '='){
            string = eval(string);
            input.value = string;
        }
        else if(e.target.innerHTML == 'AC'){
            string = "";
            input.value = string;
        }
        else if(e.target.innerHTML == 'DEL'){
            string = string.substring(0, string.length-1);
            input.value = string;
        }
        else{
            string += e.target.innerHTML;
            input.value = string;
        }
    });
});
