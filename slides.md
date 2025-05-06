---
theme: seriph
background: "https://images.unsplash.com/photo-1451187580459-43490279c0fa?q=80&w=1744&auto=format&fit=crop"
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
- **<span @click="goToSlide(22)">Month 1 Week 3</span>**
- **<span @click="goToSlide(65)">Month 2 Week 3</span>**


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

- [**Learning How to Learn**](https://www.coursera.org/learn/learning-how-to-learn) – Coursera
- [**The Front End Developer/Engineer Handbook**](https://frontendmasters.com/guides/front-end-handbook/2024/) – Frontend Masters
- [**Refactoring UI**](https://refactoringui.com/) by Adam Wathan.

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

_The return value can be a variable, array, object, string, number, boolean or even a function._

<style>
.header-title {
  color: #3B82F6;
  font-size: 2.5em;
}
</style>

---

## transition: slide-left

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

transition: slide-left

---

## Ways of Declaring Functions {.header-title}

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

transition: fade
layout: default

---

<br>

## 🔢 Arrays in Javascript {.header-title}

An array is a data structure used to store multiple comma separated values. Arrays are declared using square brackets, `[]`.

_Example:_

```js
let arr = [1, 2, 3];
```

```js
let circleFiveMembers = [
  "Zoe",
  "Deborah",
  "Funmilola",
  "Augustina",
  "Angelina",
  "OgheneO'Tega",
  "Anthony",
  "Blessing",
  "Akanmu",
  "Arnold",
  "Kachi",
  "Omogbolahan",
];
console.log(circleFiveMembers[5]); // Output: OgheneO'Tega
```

<br>

_In Javascript, an array can contain different data types._

**There are several array methods: push(), pop(), shift(), unshift(), map(), filter(), reduce(), sort(), reverse(), slice(), splice().**

<style>
.header-title {
  color: #3B82F6;
  font-size: 2.5em;
}
</style>

---

## 📌 Rest Parameters and Spread Operators{.header-title}

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

<style>
.header-title {
  color: #3B82F6;
  font-size: 2.5em;
}
</style>

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

## 🔁 Callback Functions{.header-title}

"I will call you back later!"

A callback is a function passed as an argument to another function and gets executed after the completion of a specific task or when an event occurs.

Example

```js
function handleCookies(message, acceptFn, rejectFn) {
  let result = confirm(message);
  // If user clicks 'OK'
  if (result) acceptFn();
  // If user clicks 'Cancel'
  else rejectFn();
}

handleCookies(
  "Do you accept cookies on this site?",
  () => console.log("Cookies accepted"),
  () => console.log("Cookies rejected")
);
```

`acceptFn` and `rejectFn` are functions passed as arguments to `handleCookies`. They not executed immediately but called later depending on the user's choice.

<style>
.header-title {
  color: #3B82F6;
  font-size: 2.5em;
}
</style>

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

---

transition: slide-up
layout: default

---

# Month 1 Week 2 {.header-title}

## PROMISES

A promise is an object that represents a future result of an asynchronous operation. It has 3 states. They are :

1. Pending - initial state
2. Fulfilled - successful completion
3. Rejected - Operation Failed
   <br>

### How to create a promise?

Simply:

```js
newPromise();
```

<br>

**A promise will take the function for the fulfilled and the rejected :**

```js
newPromise(resolve, reject);
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
      if (url.includes("success")) {
        resolve({ data: "Here is your data", status: 200 });
      } else {
        reject({ error: "Failed to fetch data", status: 404 });
      }
    }, 2000);
  });
}

// Using the promise
fetchData("https://api.example.com/success")
  .then((response) => {
    console.log("Success:", response.data);
  })
  .catch((error) => {
    console.log("Error:", error.error);
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
    const response = await fetchData("https://api.example.com/success");
    console.log("Data:", response.data);
    return response;
  } catch (error) {
    console.error("Error:", error);
    throw error;
  }
}

// Call the async function
getData().then((data) => {
  console.log("Processing data further");
});
```

<style>
.header-title {
  color: #EC4899;
}
</style>

---





# Month 1 Week 3 {.header-title}

## API’S AND ITS FUNCTION
### SUMMARY: { .hhh }


- The primary responsibility of a front end developer is to create pixel perfect UI and also
  to make the UI functional and usable.
- API’s are endpoints to Github. There is always a documentation on every API.
- You can make use of Github API to create a repository,and also use it to comment
- **FETCH** is used to make API’S calls .Making API’s calls is like you are talking to a particular backend/ endpoint.
- **XMLHttpRequest** can also be used to make API calls
- API’s are also used to submit forms.
- There are different ways to talk to the API’s which are : **GET**, **POST**.


<style>
.header-title {
  color: #F59E0B;
}
.hhh{
    color:green;
  }
</style>
---



**GET**


This is a single way to fetch information back to us.Example of the GET request is when you visit a browser.

  <img src="./images/pic.jpg"/>


---

# **POST**


Basically means to send the browser an information to get back another information.
the browser cannot make a POST request as a first request inside a URL tab especially.


A very good example of POST is when you fill a form or sign up by inputting your name,address,email and other data and submit,then you log in and it returns a feedback which indicates that your information has been received. i.e a token,which can further be sent to another API called USERS.Then the `Headers` must be parsed in using the token which is encrypted with the user’s details. This confirms that it's the same user registered that is logged in.


## Code
```js
Const response = await fetch (‘/api/users’ {git checkout
    method : ‘POST’,
headers : {
 ‘content-Type’ : ‘application/json’,
  }
body : JSON.stringify (user) ,
  })
const  result = await response.json ()
```

---


<br>
<br>

The code above shows the process using method POST and we get something called `headers` which is the ‘content-type’ called **AUTHORIZATION(BEARER)**.

<br>
<br>


Encryption and Decryption is used to store and reveal user ID using a form of token either cookies or local storage,session etc.
Backend must have a documentation for the frontends to rely on by providing API’s to communicate with.They are the intermediary between frontend and the database.
There are several tools that can give us the same interface of API’s, example is the **Github API Docs**.They can be used to create repositories using tokens.

---


<br>
<br>


## **Using Curls in the command line**.
- Install curl if it isn't already installed on your machine. To check if curl is installed, execute curl --version in the command line. 
- Create an access token. For example, create a personal access token or a GitHub App user access token. You will use this token to authenticate your request, so you should give it any scopes or permissions that are required to access the endpoint.


<br>
<br>

# GitHub API Request

```bash

curl --request GET \
  --url "https://api.github.com/repos/octocat/Spoon-Knife/issues" \
  --header "Accept: application/vnd.github+json" \
  --header "Authorization: Bearer YOUR-TOKEN"
```
---

<br>
<br>

- In most cases, you can use `Authorization: Bearer`or `Authorization: token` to pass a token. However, if you are passing a JSON web token (JWT), you must use Authorization: Bearer.

<br>
<br>

# URLs

Javascript provides a built in URL class that makes working with URL easier and safer.The URL object provides a convenient method to parse in URLs.


<style>
.header-title {
  color: #10B981;
}
</style>


---


## Code


```js
const url = new URL("https://example.com/products?id=123&category=books");


console.log(url.href); // "Full URL: "https://example.com/products?id=123&category=books"
console.log(url.origin); // "https://example.com"
console.log(url.protocol); // "https:"
console.log(url.hostname); // "example.com"
console.log(url.pathname); // "/products"
console.log(url.search); // "?id=123&category=books"
console.log(url.hash); // "" (empty if not present)
console.log(url.searchParams.get("id")); // "123"
console.log(url.searchParams.get("category")); // "books"


url.searchParams.set("category", "fiction"); // Update parameter
url.searchParams.append("sort", "price"); // Add new parameter
url.searchParams.delete("id"); // Remove a parameter


console.log(url.toString()); // New URL after changes


const newUrl = new URL("https://example.com/page");
newUrl.searchParams.set("user", "alice");
newUrl.searchParams.set("mode", "edit");

console.log(newUrl.toString());
// Output: "https://example.com/page?user=alice&mode=edit"
```

---

There are API's used to generate token and auntheticate ID's.We have **WEATHER API'S**,**JSONPLACEHOLDER**.
There is an npm package called **JSONSERVER** used to create API'S when there is no API that meets
our needs by creating a fake data that looks like JSON.

<br>
<br>

# TOPICS


- MODULES & JAVASCRIPT IN THE BROWSER(DOM)
- IMPORT & EXPORT (Why do they exist?)
- WHAT IS DOM?

---


<style>
.header-title {
  color: #F59E0B;
}
</style>



# Month 1 Week 4 {.header-title}

## BOM, DOM, and CSSOM

<br>

### BOM (Browser Object Model)

<br>

- BOM is the interface between JavaScript and the browser.
- It allows JavaScript to interact with the **browser itself** — such as:
  - The window
  - Tabs
  - URLs
  - Alerts

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

# CSSOM (CSS Object Model)

- CSSOM is the interface between JavaScript and CSS.
- It allows JavaScript to interact with and **manipulate CSS styles**.
- It's how the browser represents **all the CSS** (from `<style>`, external files, or JavaScript) as an object model.

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

# DOM (Document Object Model)

- DOM is the interface between JavaScript and **HTML + CSS**.
- It represents the web page as an **object tree structure**.
- JavaScript uses the DOM to read, access, and change elements on the page.
- DOM is a **tree-like structure** converted from HTML tags.
- These HTML elements are connected by **nodes** (element nodes, text nodes, etc.).

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

# The Nodes

- The entire HTML document is the **document node**, which is the **root** of the DOM.
- `<html>`, `<body>`, `<h1>`, and `<p>` are **element nodes**.
- `"Hello!"` and `"this is a paragraph"` are **text nodes**.

<style>
.header-title {
  color: #3B82F6;
  font-size: 2.5em;
}
</style>

---

transition: slide-up
layout: two-cols

---

# Example of Nodes Explanation

## Code

<br>
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS DOM</title>
</head>
<body>
    <h1 >Hello!</h1>
    <script>
        document.querySelector("h1").textContent = "New Heading!";
        document.querySelector("h1").style.color = "red";
    </script>
    <p>This is a paragraph.</p>
    <script src="index.js"></script>

</body>
</html>
```

::right::

## The nodes

![Nodes image](./images/nodes.PNG)

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

# Changing the style the content of an html page

## Code

<br>
```html
<h1 >Hello!</h1>
    <script>
        document.querySelector("h1").textContent = "New Heading!";
        document.querySelector("h1").style.color = "red";
    </script>
    <p>This is a paragraph.</p>
```

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

# Answer to the Assignment question

```js
// creating a div element

const textDiv = document.createElement("div");

// now let's create a paragragh in the div
const textPara = document.createElement("p");

// adding text
textPara.textContent =
  "See you on the other side, where we will discuss events in JavaScript. May the force be with you.";
textDiv.appendChild(textPara);

document.body.appendChild(textDiv);
(textPara.style.fontFamily = "Georgia"), serif;
textPara.style.fontStyle = "italic";
```

<style>
.header-title {
  color: #3B82F6;
  font-size: 2.5em;
}
</style>

---

transition: fade
layout: center
class: text-center

---

# JavaScript Modules and Related Concepts

### WEEK 1 - EXTRA CLASS

---

## 1. Modules and Modularity

**Modularity** refers to breaking down a program into smaller, manageable, and reusable pieces (modules).

<!-- Add a list with staggered animation -->
<v-clicks>

**Why use modularity?**

- Improved code organization
- Easier maintenance and debugging
- Reusability across projects

</v-clicks>

---

<!-- Add fade in animation to code blocks -->
<div v-motion :initial="{ opacity: 0 }" :enter="{ opacity: 1 }">

```javascript
// math.js (module)
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}
```

<br>

```javascript
// app.js (main file)
import { add, subtract } from "./math.js";
```

</div>

## <!-- Add slide transitions -->

<br>

## 2. Bundlers

<!-- Add click animations to list items -->
<v-clicks>

**Popular bundlers:**

- Webpack
- Rollup
- Vite
- Parcel

</v-clicks>

---

### Why use bundlers?

- Support for modular code in environments that don't support modules natively.
- Code splitting and optimization (tree-shaking, minification).

<br>

### Webpack Example (Conceptual):

<br>

```javascript
// index.js
import { greet } from "./utils.js";

greet("World");
```

<br>

```javascript
// utils.js
export function greet(name) {
  console.log(`Hello, ${name}!`);
}
```

---

## 3. Imports and Exports

### a) Named Export/Import

```javascript
// math.js
export function add(a, b) {
  return a + b;
}
export function subtract(a, b) {
  return a - b;
}
```

```javascript
// app.js
import { add, subtract } from "./math.js";
```

<br>

### b) Renamed Exports/Imports

```javascript
// math.js
function add(a, b) {
  return a + b;
}
export { add as sum };
```

```javascript
// app.js
import { sum as addNumbers } from "./math.js";
```

---

### c) Default Export/Import

<br>

```javascript
// logger.js
export default function log(message) {
  console.log(message);
}
```

<br>

```javascript
// app.js
import log from "./logger.js";
```

<br>

### d) Dynamic Import

<br>

```javascript
// app.js
button.addEventListener("click", async () => {
  const module = await import("./math.js");
  console.log(module.add(2, 3));
});
```

---

## 4. ESM (ECMAScript Modules)

**ESM** is the standardized module system for JavaScript (using `import`/`export`). It’s supported in modern browsers and Node.js.

### Enabling ESM in Node.js:

You can:

- Use the `.mjs` file extension **or**
- Add `"type": "module"` in `package.json`

<br>

```json
// package.json
{
  "type": "module"
}
```

---

### Example:

<br>
<br>

```javascript
// utils.mjs or utils.js (with type module in package.json)
export const greet = (name) => `Hello, ${name}!`;
```

<br>

```javascript
// main.mjs or main.js
import { greet } from "./utils.mjs";
console.log(greet("ESM"));
```

---

## 5. Package.json

The `package.json` file is the configuration file for Node.js projects. It defines:

- Project metadata (name, version, description)
- Dependencies and devDependencies
- Scripts for running tasks
- Module type (CommonJS or ESM)
- Entry points (e.g., `main`, `module`)

---

### Example:

<br>

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "description": "A sample project demonstrating modules",
  "type": "module",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",
    "build": "webpack"
  },
  "dependencies": {
    "lodash": "^4.17.21"
  },
  "devDependencies": {
    "webpack": "^5.0.0"
  }
}
```

---

# Month 2 Week 1 {.header-title}

## Cont. of DOM in JavaScript (Selecting an Element by Its Unique Identifier (Id) and Styling It Within JavaScript)

### Summary:

DOM (also known as **Document Object Model**) is the object representation of HTML.  
An HTML document could be declared with an empty body.  
The **Id** of each empty element node can then be selected using `querySelector` or `getElementById`.  
The `innerHTML` can then be assigned a value after a variable has been declared.  
The selected elements can be styled as preferred within the JavaScript code.

---

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

<br>
### Example of Selecting an Element by Its Unique Identifier (Id) Using `querySelector` and `getElementById`, and Styling the Selected Elements...

---

You can select HTML elements by their unique `id` using either `querySelector` or `getElementById`. After selection, you can modify their content and apply styles directly with JavaScript.

```js
//Selecting elements by id using the querySelector
const divElement = document.getElementById("container");
const h1Element = document.querySelector("#circle_5");
const h2Element = document.getElementById("semester_2");
//throw an error if elements are not found
if (h1Element === null) {
}
if (h2Element === null) {
}
//If found, display these messages into the inner text and style it
divElement.style =
  "Justify-content: center; text-align: center; background-color: #f7f7f7; padding: 20px; margin: 20px 0; border: 1px solid #ccc;border-radius: 15px;";
h1Element.innerHTML = "Altschool FrontEnd Circle-5";
h2Element.innerHTML =
  "Summary of what we have learnt since the beginning of 2nd semester.";
```

---

# React in Vanilla Projects

## Libraries vs Frameworks

- **Library**: A set of tools where _you control the flow_.

  - Examples: React, Svelte, Angular, Vue

- **Framework**: An opinionated structure that _controls the flow_.
  - Example: Next.js (built on React)

## Why React?

- 🔹 **Simple**: Focuses on UI rendering
- 🔹 **Popular**: Strong community, resources, and job market
- 🔹 **Performance**: Uses Virtual DOM for efficient rendering
- 🔹 **Flexible**: Build your app your way

---

## Core Concepts

- **UI** = What user sees
- **State** = Data that powers the UI
- React turns `UI + State` into **components** (functions that return JSX)

---

## Vanilla JS to React (Example)

```js
function mk(type) {
  const el = document.createElement(type);
  el.textContent = "hello world";
  return el;
}
document.body.appendChild(mk("h6"));
```

## Rewriting with Props

```js
function mk(type, props) {
  const el = document.createElement(type);
  if (props) Object.assign(el, props);
  return el;
}

const el = mk("h1", { textContent: "Hello World", className: "title" });
document.body.appendChild(el);
```

---

# React Setup & Vite

## Build Tools

- 🛠️ **Purpose**: Compile, bundle & optimize apps
- Examples: Webpack, Vite, TurboRepo, Parcel, Rspack

## Why Vite?

- ⚡ Fast, uses native ES modules
- 🔧 Zero-config setup
- Supports React, Vue, etc.

---

## Install Vite (Vanilla + JS)

```bash
npm create vite@latest

# Then:
cd vite-project
npm install
npm run dev
```

- Visit your app on: `http://localhost:5173`
- Build production: `npm run build`

---

## Add React via CDN

### Development

```html
<script
  crossorigin
  src="https://unpkg.com/react@18/umd/react.development.js"
></script>
<script
  crossorigin
  src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"
></script>
```

### Production

```html
<script
  crossorigin
  src="https://unpkg.com/react@18/umd/react.production.min.js"
></script>
<script
  crossorigin
  src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"
></script>
```

---

# React DOM Methods & Components

## Creating React Elements

```js
const nemElement = React.createElement("h1", null, "I am a new element");
console.log(nemElement); // Logs a React object, not HTML
```

## Rendering Elements

```js
const rootElement = document.querySelector("#app");
const root = ReactDOM.createRoot(rootElement);
root.render(nemElement);
```

## Creating Components

```js
function App() {
  return React.createElement("div", null, "This is a React Component");
}

const root = ReactDOM.createRoot(document.querySelector("#app"));
root.render(React.createElement(App));
```

---

## React State

```js
const [todos, setTodos] = React.useState([]);
// Default values: [], '', null, 0
```

- useState returns a pair `[state, setState]`
- Individual logic placed in **handlers**

---

# Month 2 Week 3 {.header-title}

## Cont. of BUNDLERS (VITE) & TO-DO APP PR REVIEW

### Summary:

<br>

# 1. Bundlers Overview (Continuation: Vite)
<br>
Browsers have limitations; bundlers help manage modern JavaScript features and dependencies.

**Common bundlers:** Browserify, Webpack, Parcel, Vite

## Benefits of bundlers:

- Lazy loading (only load code when needed)
- Dynamic imports for better performance

<style>
.header-title {
  color: #3B82F6;
  font-size: 2.5em;
}
</style>

---

## 2. Focus on Vite

Vite is a modern and fast bundler optimized for speed and simplicity.

## 3. Creating a Vite Project

**Long method:**


```bash 
mkdir new_project
```

```bash 
cd new_project
```

```bash 
npm init -y

```

```bash 
npm install --save-dev vite

```

```bash 
touch index.html index.css index.js

```

---

## Set up build scripts in `package.json`:

```json
"scripts": {
  "dev": "vite",
  "build": "vite build",
  "preview": "vite preview"
}
```

## Start the development server:

```bash
npm run dev
```

*You can use* **`pnpm`** *instead of* **`npm`** *to initialize and install dependencies.*

## Shortcut method: Creating a Vite Project

```bash
npm create vite@latest new_project --template vanilla
```

```bash
# or using pnpm
pnpm create vite@latest new_project --template vanilla
```

```bash
cd new_project
```

---

## Shortcut method: Creating a Vite Project cont.
<br>

```bash
npm install
```

```bash
npm run dev
```

## 4. Pull Request Review – To-do App (Mariam’s Branch)
<br>
- We cloned and checked out Mariam’s `vite` branch.
- Added `.gitignore` to exclude `node_modules` and other unnecessary files from version control.
- To list all files (including hidden ones like `.git`):

```bash
ls -la
```

---

## Contributions

### Mariam:
- Modularized the project structure  
- Enabled double-click to edit feature  
- Implemented `localStorage` saving  

### Osawawo:
- Added checkbox functionality

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
