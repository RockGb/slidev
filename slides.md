---
theme: seriph
background: 'https://images.unsplash.com/photo-1451187580459-43490279c0fa?q=80&w=1744&auto=format&fit=crop'
# some information about your slides (markdown enabled)
title: AltSchool Frontend Circle 5
info: |
  ## Assignment Presentation.
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
transition: slide-left
mdc: true
---

# AltSchool Frontend Circle 5

**Assignment Presentation**

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Press Space for next page <carbon:arrow-right />
</div>
---

# Table of Content {.transition-title}

- **<span @click="goToSlide(1)">Front Page</span>**
- **<span @click="goToSlide(2)">Table of Contents</span>**
- **<span @click="goToSlide(3)">Month 1 Week 1</span>**
- **<span @click="goToSlide(7)">Month 1 Week 2</span>**
- **<span @click="goToSlide(10)">Month 1 Week 3</span>**

<script setup>
const goToSlide = (index) => {
  $slidev.nav.go(index)
  }
</script>

<style>
.transition-title {
  color: rgb(0, 255, 0); /* Green color for transition title */
}
span {
  cursor: pointer;
  color: rgb(255, 255, 255);
  text-decoration: none;
}
span:hover {
  color: rgb(16, 24, 235);
}
</style>

---
transition: fade
layout: default
---

# Month 1 – Week 1 Recap {.header-title}

The Second Semester officially kicks off!

## 📚 Recommended Resources {.header-title}
<br>

- **Learning How to Learn** – Coursera  
- **The Front End Developer/Engineer Handbook** – Frontend Masters  
- **Refactoring UI** by Adam Wathan.


<br>


> **Goal:** Master JavaScript before moving on to React.  
> **Semester Expectation:** Build and deploy React applications successfully.

<style>
.header-title {
  color: #3B82F6;
  font-size: 2.5em;
}
</style>
---

ANSWERS TO QUESTIONS (CONCERNS) {.header-title}

## ⚙️ Return Statement in JavaScript {.header-title}

The `return` statement  
- The return statement ends function execution and specifies a value to be called to the function caller.
- The last line in a function must be a return statement.

**Syntax:**
```js
function functionName() {
  return value;
}
```

*The return value can be a variable, array, object, string, number, boolean or even a function.*

**Example:**
```js
function add(a, b) {
  return a + b;
}

let sum = add(3, 5);
console.log(sum); // Output: 8

```



<style>
.header-title {
  color: #3B82F6;
  font-size: 2.5em;
}
</style>
---
transition: slide-left
---
*If return statement is omitted in a function, it returns undefined when called.*

**Example:**
```js
function greet(name) {
console.log("Hello, " + name + "!");
}

let result = greet("Zoe");
console.log(result); // Output: undefined
```

## Ways of Declaring Functions {.header-title}

There are several ways of creating functions in Javascript:<br>

- **Function Declaration:** A named function is defined with the **'function'** keyword 
```js
function getUsername(user) {
  return user.username;
}
```
<br>

- **Function Expression:** A function assigned to a variable
```js
const getUsername = function(user) {
  return user.username;
};
```


<style>
.header-title {
  color: #3B82F6;
}
</style>

---
transition: fade
layout: default
---

- **Arrow Function:** A concise way of writing function expression syntax, introduced in ES6.
```js
const getUsername = (user) => {
  return user.username;
};
```
- **One Line Arrow Function (Implicit Return):**  Function written on a single line, has implicit return statement.
```js
const getUsername = user => user.username; 
```
<br>

## Arrays in Javascript {.header-title}

An array is a data structure used to store multiple comma separated values. Arrays are declared using square brackets, []. 

*Example:*
```js
let arr = [1, 2, 3]
```

```js
let circleFiveMembers = ["Zoe", "Deborah", "Funmilola", "Augustina", "Angelina", "OgheneO'Tega", "Anthony", "Blessing", "Akanmu", "Arnold", "Kachi"]
console.log(circleFiveMembers[5]) // Output: OgheneO'Tega
```
<br>

*In Javascript, an array can contain different data types.*

**There are several array methods: push(), pop(), shift(), unshift(), map(), filter(), reduce(), sort(), reverse(), slice(), splice().**



<style>
.header-title {
  color: #3B82F6;
  font-size: 2.5em;
}
</style>

---
transition: slide-up
layout: default
---

# Month 1 Week 2 {.header-title}

## PROMISES
1. Pending - initial state
2. Fulfilled - successful completion
3. Rejected - Operation Failed
<br>

### How to create a promise?
Simply: 
```js
newPromise()

```
<br>

**A promise will take the function for the fulfilled and the rejected :**
```js
newPromise(resolve, reject)
```

<br>

Contd on next page



<style>
.header-title {
  color: #10B981;
}
</style>

---
transition: fade-out
layout: two-cols
---
Sample syntax:

```js
Const myPromise = newPromise ((resolve, reject) => {
If () {
resolve(value); // promise is fulfilled with value
} else {
reject(error); // promise is rejected with error
}
});
```
<br>

::right::

Sample Code:
```js
function fetchData(url) {
  return new Promise((resolve, reject) => {
    // Simulating network request
    setTimeout(() => {
      if (url.includes('success')) {
        resolve({ data: 'Here is your data', status: 200 });
      } else {
        reject({ error: 'Failed to fetch data', status: 404 });
      }
    }, 2000);
  });
}

// Using the promise
fetchData('https://api.example.com/success')
  .then(response => {
    console.log('Success:', response.data);
  })
  .catch(error => {
    console.log('Error:', error.error);
  });

```

<style>
.header-title {
  color: #8B5CF6;
}
</style>

---
transition: fade-out
layout: default
---

### Async / Await
It is a Modern way to write Promises

**Note** : Putting 'async' in front of a function automatically makes it a **Promise**.

```js
async function getData() {
  try {
    const response = await fetchData('https://api.example.com/success');
    console.log('Data:', response.data);
    return response;
  } catch (error) {
    console.error('Error:', error);
    throw error;
  }
}

// Call the async function
getData().then(data => {
  console.log('Processing data further');
});
```

<style>
.header-title {
  color: #EC4899;
}
</style>

---
transition: slide-up
layout: default
---

# Month 1 Week 3 {.header-title}

## Text
-  1
-  2
-  3

### Code Example
```js
class Feature {
}
```

<style>
.header-title {
  color: #F59E0B;
}
</style>

---
transition: slide-left
layout: two-cols
---

# Month 1 Week 4 {.header-title}

## Documentation

::right::

## Code
```js
const final = {
}
```

<style>
.header-title {
  color: #EF4444;
}
</style>

---
transition: fade
layout: center
class: text-center
---

# Thank You! {.thank-you}

## Questions & Discussion

<style>
.thank-you {
  background: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  font-size: 3em;
}
</style>

---
transition: fade-out
layout: default
---

# Month 2 Week 1 {.header-title}

## Cont. of DOM in JavaScript (Selecting an Element by Its Unique Identifier (Id) and Styling It Within JavaScript)

### Summary:

DOM (also known as **Document Object Model**) is the object representation of HTML.  
An HTML document could be declared with an empty body.  
The **Id** of each empty element node can then be selected using `querySelector` or `getElementById`.  
The `innerHTML` can then be assigned a value after a variable has been declared.  
The selected elements can be styled as preferred within the JavaScript code.

### Example of a Document with an Empty Body

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="./index.js" defer></script>
    <title>Dom in JavaScript</title>
  </head>
  <body>
    <div id="container">
    <h1 id="circle_5"></h1>
    <p id="semester_2"></p>
</div>
  </body>
</html>
```
## Example of Selecting an Element by Its Unique Identifier (Id) Using `querySelector` and `getElementById`, and Styling the Selected Elements...

You can select HTML elements by their unique `id` using either `querySelector` or `getElementById`. After selection, you can modify their content and apply styles directly with JavaScript.

```js
//Selecting elements by id using the querySelector
const divElement = document.getElementById("container");
const h1Element = document.querySelector("#circle_5");
const h2Element = document.getElementById("semester_2");
//throw an error if elements are not found
if (h1Element === null) {
};
if (h2Element === null) {
}
//If found, display these messages into the inner text and style it
divElement.style =
  "Justify-content: center; text-align: center; background-color: #f7f7f7; padding: 20px; margin: 20px 0; border: 1px solid #ccc;border-radius: 15px;";
h1Element.innerHTML = "Altschool FrontEnd Circle-5";
h2Element.innerHTML =
  "Summary of what we have learnt since the beginning of 2nd semester.";
  ```