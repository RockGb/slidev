---
layout: center
transition: fade-out
---

# [Month 1 Week 1]{.gradient-text}

<!-- CSS styling for .gradient-text class -->
<style>
    .gradient-text {
      background: linear-gradient(45deg, #4EC5D4 10%, #008080 20%);
      -webkit-background-clip: text;
      -moz-background-clip: text;
      -webkit-text-fill-color: transparent;
      -moz-text-fill-color: transparent;
      font-size: 2em; 
    }
   
</style>

---

**The Second Semester officially kicks off!**

## [📚 Recommended Resources]{.text-teal-400}

<br>

<v-clicks>

- [**Learning How to Learn**](https://www.coursera.org/learn/learning-how-to-learn) – Coursera

- [**The Front End Developer/Engineer Handbook**](https://frontendmasters.com/guides/front-end-handbook/2024/) – Frontend Masters
- [**Refactoring UI**](https://refactoringui.com/) by Adam Wathan.

</v-clicks>

<br>

> **Goal:** Master JavaScript concepts before moving on to React.

<br> 

> **Semester Expectation:** Build and deploy React applications successfully.

---

## [⚙️ Return Statement in JavaScript]{.text-teal-400}

<br>

The `return` statement

- The return statement ends function execution and specifies a value to be called to the function caller.
- The last line in a function must be a return statement.
- Any statement wriiten after the return statement will not be executed
- The return statement only returns one value.

**Syntax:**

```js
function functionName() {
  return value;
}
```

_The return value can be a variable, array, object, string, number, boolean or even a function._

---

**Example:**

```js 
function add(a, b) {
  return a + b;
}

let sum = add(3, 5);
console.log(sum); // Output: 8
```

_If return statement is omitted in a function, it returns undefined when called._

**Example:**

```js 
function greet(name) {
  console.log("Hello, " + name + "!");
}

let result = greet("Zoe");
console.log(result); // Output: undefined
```
---

### Ways of Declaring Functions {.text-teal-400}

<br>

- **Function Declaration:** A named function is defined with the **'function'** keyword

```js
function getUsername(user) {
  return user.username;
}
```

- **Function Expression:** A function assigned to a variable

```js
const getUsername = function (user) {
  return user.username;
};
```

- **Arrow Function:** A concise way of writing function expression syntax, introduced in ES6

```js
const getUsername = (user) => {
  return user.username;
};
```

- **One Line Arrow Function(Implicit Return):** Function written on a single line, has implicit return statement.

```js
const getUsername = (user) => user.username;
```

---

## 🔢 Arrays in Javascript {.text-teal-400}

<br>

An array is a data structure used to store multiple comma separated values. Arrays are declared using square brackets, `[]`.

_Example:_

```js
let arr = [1, 2, 3];
```

```js
let circleFiveMembers = [
  "Zoe", "Deborah", "Funmilola", "Augustina", "Angelina", "OgheneO'Tega", "Anthony", "Blessing", "Akanmu" "Arnold", "Kachi", "Omogbolahan",];
console.log(circleFiveMembers[5]); // Output: OgheneO'Tega
```

<br>

_In Javascript, an array can contain different data types._

*There are several array methods: push(), pop(), shift(), unshift(), map(), filter(), reduce(), sort(), reverse(), slice(), splice().*

---

## 📌 Rest Parameters and Spread Operators{.text-teal-400}

<br>

Rest Parameters represents a concept which allows a function to accept any number of arguments and store in an array. Rest Parameters are used in functions with unknown number of arguments.

Syntax:

`function myFunction (...args)`

Example:

```js
// function to sum up multiple numbers
function sum(...nums) {
  return nums.reduce((a, b) => a + b, 0);
}

console.log(sum(1, 2, 3)); // Expected Output: 6
```

_It is important to note that only one rest parameter is allowed in a function definition and it must be the last parameter in a function's parameter list._

---

Spread Operator (`...`) expands an iterable like an array or string into more elements. Iterables are objects that can be looped over especially using the for...of loop.

<br>

```js
const arr = [1, 2, 3];
// Using for of loop
for (const item of arr) {
  console.log(item);
}
// Output: 1 2 3
```

<br>

### Spread operator can be used to copy (clone) arrays

```js
let arr = [1, 2, 3];
let newArr = [...arr];
console.log(newArr); // Output: 1, 2, 3
```

---

### Spread operator can be used to merge arrays

<br>
```js
let girls = ["Jane", "Rose", "Blessing"];
let boys = ["John", "David", "Samuel"];
let allStudents = [...girls, ...boys];
console.log(allStudents); // [ "Jane", "Rose", "Blessing", "John", "David", "Samuel"]
```
<br>

### Spread operator can be used to add elements to an array

<br>

```js
const numbers = [1, 2, 3];
const newNumbers = [...numbers, 4];
console.log(newNumbers); // [1, 2, 3, 4]
```

Spread operator can also be used with objects.

---

## 🔁 Callback Functions{.text-teal-400}

A callback is a function passed as an argument to another function and gets executed after the completion of a specific task or when an event occurs.

<br>

<img src="../images/callback.png" style="width: 40%; margin: auto"> 


---

**Code Snippet**
```js {all|1-4|6-14|14-20|all}
// Define a function called orderPizza that takes another function (callback) as a parameter
function orderPizza(callback) {
  // Log the initial step of placing the order
  console.log("Ordering pizza...");

  // Simulate a delay of 3 seconds (3000 milliseconds) to prepare the pizza
  setTimeout(() => {
    // Log that the pizza is ready after the delay
    console.log("Pizza is ready!");

    // Call the callback function passed to orderPizza
    callback(); // This represents the "call back" when the pizza is ready
  }, 3000);
}

// Call the orderPizza function and pass a callback function as an argument
orderPizza(() => {
  // This is the callback function — it runs after the pizza is ready
  console.log("Got the callback! Eating pizza now.");
});

```

---

Callbacks are mostly used in asynchronous operations (tasks running independently)

Example using `setTimeout` function

```js
function showMessage() {
  console.log("Hello after 3 seconds!");
}

setTimeout(showMessage, 3000);
```

`setTimeout` is a built-in asynchronous function in Javascript and it takes in two parameters - a callback function and a delay.

_Note if `showMessage()` is added the function will be executed immediately and return undefined._

Callbacks are also used in event listeners

```js
document
  .getElementById("myBtn")
  .addEventListener("click", () => console.log("Button clicked!"));
```

The function (callback) passed as a parameter to `addEventListener` will only be executed when the button is clicked.

