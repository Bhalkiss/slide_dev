---
layout: center
title: Javascript Journey with Circle 16
theme: seriph
---

# Javascript Journey with Circle 16

---
layout: center
title: Table of Contents
---

# Table of Contents
- Functions 
- Arrays and its methods
- DOM Manipulation
- Event Listeners
- Fetch API
- Promises
- Async/Await
- Error Handling
- API calls


---
layout: center
title: Functions
---
# Functions
functions are reusable blocks of code that perform a specific task. They can take inputs (parameters) and return outputs (values). Functions help in organizing code, making it more readable and maintainable.

```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
console.log(greet("Circle 16")); // Output: Hello, Circle 16!       
```
--- layout: center
title: Function Expressions
---
# Function Expressions
Function expressions are similar to function declarations, but they are not hoisted. They can be anonymous or named. Function expressions can be assigned to variables, passed as arguments, or returned from other functions.

```javascript
const greet = function(name) {
    return `Hello, ${name}!`;
}
console.log("john"); // Output: Hello, john!
```
---
layout: center
title: creating a function
---
# creating a function
there are two ways to create a function in JavaScript
 - function declarations 
 - function expressions.
 
  A function declaration defines a named function, while a function expression defines a function that can be anonymous or named.

```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
console.log(greet("Circle 16")); // Output: Hello, Circle 16!       
```

```javascript
const greet = function(name) {
    return `Hello, ${name}!`;
}
console.log(greet("Circle 16")); // Output: Hello, Circle 16!       
```
---
layout: center
title: Arrays
---
# Arrays 
Arrays are used to store multiple values in a single variable. They can hold different data types, including numbers, strings, and objects. JavaScript provides various methods to manipulate arrays, such as push(), pop(), shift(), unshift(), splice(), slice(), and forEach().

```javascript
const fruits = ["apple", "banana", "orange"];
fruits.push("grape"); // Adds "grape" to the end of the array
console.log(fruits); // Output: ["apple", "banana", "orange", "grape"]
fruits.pop(); // Removes the last element from the array
console.log(fruits); // Output: ["apple", "banana", "orange"]       
``` 

```javascript
const quotes = [
  "The worst Tragedy in life is not death but a life without a reason.",
  "we are either getting better or getting worse, pick your poison.",
  "dont stop when you are tired, stop when you are done.",
  "Your time is limited, so don’t waste it living someone else’s life."
];

function getRandomQuote() {
  const randomIndex = Math.floor(Math.random() * quotes.length);
  console.log(`Quote: "${quotes[randomIndex]}"`);
}


getRandomQuote();
```
---
layout: center
title: DOM Manipulation
---
# DOM Manipulation
The Document Object Model (DOM) represents the structure of a web page. JavaScript can manipulate the DOM to change the content, structure, and style of a web page dynamically. Common DOM manipulation methods include getElementById(), querySelector(), createElement(), appendChild(), and removeChild().

```html
<h2 id="heading">Hello, World!</h2>
<button onclick="changeText()">Click Me</button>

```
```javascript
function changeText() {
  document.getElementById("heading").innerText = "Text changed via DOM!";
}
```

what the above code does:
- The h2 has an id="heading"
- The button triggers the changeText() function
- document.getElementById("heading").innerText changes the heading’s text




