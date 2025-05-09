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
- Objects and its methods
- Arrays and its methods
- DOM Manipulation
- Event Listeners
- Fetch API
- Promises
- Async/Await
- Error Handling
- API calls
- API calls with Async/Await
- API calls with Axios
- API calls with Axios and Async/Await
- callbacks
- Summary


---
layout: center
title: Functions
---
# Functions
functions are reusable blocks of code that perform a specific task. 
They can take inputs (parameters) and return outputs (values). 
Functions help in organizing code, making it more readable and maintainable.

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
Function expressions are similar to function declarations, but they are not hoisted. They can be anonymous or named. 
Function expressions can be assigned to variables, passed as arguments, or returned from other functions.

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
title: objects
---
# Objects and its methods
In JavaScript, an object is a standalone entity, with properties and values. 
Objects are used to store keyed collections of various data and more complex entities. 
Each property is defined as a key-value pair.
```javascript
const person = {
  name: "Alice",
  age: 25,
  isStudent: true
};
```
# Accessing and Modyfying properties
You can access and modify object properties using dot notation or bracket notation.

```javascript
const car = { brand: "Toyota", color: "blue" };
console.log(car.brand);      // "Toyota"
car.color = "red";           // Modify property
console.log(car["color"]);   // "red"
```
# Adding and Deleting properties
You can add new properties or delete existing ones using the following syntax:

```javascript
const user = { name: "John" };
user.age = 30;               // Add property
delete user.name;            // Remove property
console.log(user);           // { age: 30 }
```
Object.keys(), Object.values(), Object.entries()
- Object.keys() returns an array of a given object's own property names.
- Object.values() returns an array of values.
- Object.entries() returns an array of [key, value] pairs.
```javascript

hasOwnProperty()
The hasOwnProperty() method returns a boolean indicating whether the object has the specified property as its own (not inherited).
```javascript 
const book = { title: "JS Guide" };
console.log(book.hasOwnProperty("title")); // true
console.log(book.hasOwnProperty("author")); // false

```
 Summary
- Objects are key-value pairs used for structured data.
- JavaScript offers many built-in methods to manipulate and inspect objects.
- Mastering object handling is essential for working with complex data in real-world applications.

---
layout: center
title: Arrays
---
# Arrays 
Arrays are used to store multiple values in a single variable.
 They can hold different data types, including numbers, strings, and objects.
  JavaScript provides various methods to manipulate arrays, 
  such as push(), pop(), shift(), unshift(), splice(), slice(), and forEach().

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
Accessing and Modifying Arrays
You can access elements in an array using square brackets and their index. 
JavaScript arrays are mutable, meaning you can change their contents after creation.
```javascript
const fruits = ["apple", "banana", "orange"];
console.log(fruits[1]); // Outputs: "banana"
fruits[2] = "mango"; // Changes "orange" to "mango"
console.log(fruits); // Outputs: ["apple", "banana", "mango"]
```


---
layout: center
title: DOM Manipulation
---
# DOM Manipulation
The Document Object Model (DOM) represents the structure of a web page.
 JavaScript can manipulate the DOM to change the content, structure, and style of a web page dynamically. 
 Common DOM manipulation methods include getElementById(), querySelector(), createElement(), appendChild(), and removeChild().

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

---
layout: center
title: Event Listeners
---
# Event Listeners
Event listeners are functions in JavaScript that wait for specific actions (called events) to happen on a web page, 
like a user clicking a button, typing in a form, or moving the mouse.

They allow your page to respond to those events dynamically.

simple examples are:
- clicks
- key presses
- mouse movements
- form submissions

```html
<button id="myBtn">Click Me</button>

```

```javascript

<script>
  const button = document.getElementById("myBtn");

  button.addEventListener("click", () => {
    alert("You clicked the button!");
  });
</script>
```

DOM Property Event Handlers
This approach uses JavaScript to assign a handler to a DOM element’s event.

```javascript  
const btn = document.getElementById("myBtn");

btn.onclick = function() {
  console.log("Button was clicked");
}; 
```
addEventListener() Method
This modern method allows multiple handlers and supports advanced options.
```javascript
const btn = document.getElementById("myBtn");

btn.addEventListener("click", function() {
  console.log("Clicked using addEventListener!");
});
```
Removing Event Listeners
To remove an event, use the same function reference that was added.
```javascript
function greet() {
  console.log("Hello!");
}

btn.addEventListener("click", greet);
btn.removeEventListener("click", greet);
``` 

The Event Object
Every event handler receives an event object with info like the type and target of the event.

```javascript
document.addEventListener("click", function(event) {
  console.log("Element clicked:", event.target);
  console.log("Event type:", event.type);
});
```
 Accessing and Modifying Arrays
You can access elements in an array using square brackets and their index. 
JavaScript arrays are mutable, meaning you can change their contents after creation.

```javascript
const fruits = ["apple", "banana", "orange"];
console.log(fruits[1]); // Outputs: "banana"
fruits[2] = "mango"; // Changes "orange" to "mango"
console.log(fruits); // Outputs: ["apple", "banana", "mango"]

```
Common Array Methods 
JavaScript provides a wide range of built-in array methods to perform operations such as adding, 
removing, transforming, and iterating through elements.
Some of the most commonly used ones are:
- push(), pop()
- shift(), unshift()
- slice(), splice()
- map(), filter(), reduce()
- forEach(), find(), includes()

---
layout: center
title: Fetch API
---
# Fetch API
The Fetch API is a modern way to make network requests in JavaScript. 
It allows you to retrieve data from a server asynchronously, making it easier to work with APIs and handle responses.

```javascript
fetch("https://api.example.com/data")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error("Error:", error));
```  
 Removing Event Listeners
To remove an event, use the same function reference that was added.
```javascript
function greet() {
  console.log("Hello!");
}

btn.addEventListener("click", greet);
btn.removeEventListener("click", greet);
```

---
layout: center 
title: Promises
---
# Promises
A Promise represents a value that may be available now, later, or never. 
It provides .then() and .catch() methods to handle success or failure.
```javascript
const getData = new Promise((resolve, reject) => {
  setTimeout(() => {
    let success = true;
    if (success) {
      resolve("Data received!");
    } else {
      reject("Something went wrong.");
    }
  }, 1500);
});
getData
  .then(response => console.log(response))
  .catch(error => console.error(error));

```

---
layout: center
title: Async/Await
---
# Async/Await
Async/Await is a modern way to work with Promises, making asynchronous code easier to read and write. 
The async keyword is used to declare an asynchronous function, and the await keyword is used to wait for a Promise to resolve.

```javascript
async function fetchData() {
  try {
    const response = await fetch("https://api.example.com/data");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error:", error);
  }
}
fetchData();
```
---
layout: center
title: Error Handling
---
# Error Handling    
Error handling is essential in JavaScript to manage unexpected situations gracefully. 
The try...catch statement allows you to catch errors and handle them without crashing the program.

```javascript
try {
  // Code that may throw an error
  const result = riskyFunction();
  console.log(result);
} catch (error) {
  // Handle the error
  console.error("An error occurred:", error.message);
}
```


---
layout: center
title: API Calls
---
# API Calls                 
API calls allow you to interact with external services and retrieve or send data. 
You can use the Fetch API or libraries like Axios to make API calls in JavaScript.

```javascript           
fetch("https://api.example.com/data")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error("Error:", error));
```
--- 
layout: center      
title: API Calls with Async/Await
---
# API Calls with Async/Await
API Calls with Async/Await
The Fetch API can be used with async/await for better readability and error handling.      

```javascript
async function fetchData() {
  try {
    const response = await fetch("https://api.example.com/data");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error:", error);
  }
}
fetchData();
```
---
layout: center
title: API Calls with Axios
---
# API Calls with Axios                          
Axios is a popular library for making HTTP requests in JavaScript.
It simplifies the process of making API calls and handling responses.

```javascript           
axios.get("https://api.example.com/data")
  .then(response => console.log(response.data))
  .catch(error => console.error("Error:", error));
``` 
---          
layout: center
title: API Calls with Axios and Async/Await
---
# API Calls with Axios and Async/Await

```javascript
async function fetchData() {
  try {
    const response = await axios.get("https://api.example.com/data");
    console.log(response.data);
  } catch (error) {
    console.error("Error:", error);
  }
}
fetchData();
```
---
layout: center
title: Callbacks    
---
# Callbacks
Callbacks are functions passed as arguments to other functions. They allow you to execute code after a certain task is completed, enabling asynchronous programming.

```javascript
function fetchData(callback) {
  setTimeout(() => {
    const data = "Data received!";
    callback(data);
  }, 2000);
}
fetchData((data) => {
  console.log(data); // Output: Data received!
});
```

---
layout: center
title: Summary
---
# Summary
- Functions are reusable blocks of code that perform specific tasks.
- Arrays store multiple values and provide various methods for manipulation.
- DOM manipulation allows you to change the structure and content of a web page dynamically.
- Event listeners respond to user actions on a web page.
- The Fetch API enables asynchronous network requests to retrieve data from servers.
- Promises represent values that may be available now, later, or never.  
- Async/Await simplifies working with Promises, making asynchronous code easier to read.    
- Error handling is essential to manage unexpected situations gracefully.
- API calls allow interaction with external services to retrieve or send data.
- Error handling is crucial for managing unexpected situations gracefully.
- API calls can be made using the Fetch API or Axios, and both can be used with async/await for better readability.
- API calls can be made using the Fetch API or Axios, and both can be used with async/await for better readability

