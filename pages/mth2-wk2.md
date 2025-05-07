---
layout: center
transition: fade-out
---

# [Month 2 Week 2]{.gradient-text}

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

## [📝 Building a Todo With HTML, CSS and Javascript]{.text-teal-400}

<br>

A Todo Application would have an input field, an add and delete button and a list of possible todo’s. The aim was to build a todo application to depict what form submission does in javascript


### Form Submission Event and Methods

`Form Submission Methods` lets users send data to a server for processing
. JavaScript handles form submission in two main ways

- Using the submit event
- Using the form.submit() method

The `submit event` is triggered when a form is submitted. It’s often used to validate form data or prevent the default action to handle it with JavaScript instead

Forms are submitted either by:

- Clicking the Submit button
- Pressing Enter while focused on an input field

---

```js
// Import the form submission handler function
import { todoSubmitHandler } from "./src/submitHandler.js";

// Select the form and todo list elements
let todoForm = document.querySelector("#todoForm");
let todoList = document.querySelector("#todoList");

// ✅ Attach the form submission event listener (outside async function)
if (todoForm) {
  todoForm.addEventListener("submit", (e) =>
    todoSubmitHandler(e, todoForm, todoList)
  );
} else {
  console.warn("#todoForm element not found");
}

// ✅ Attach the form submission event listener again inside async function
(async function main() {
  let sum = await import("./src/sum.js");
  console.log(sum.default(2, 5));

  todoForm.addEventListener("submit", todoSubmitHandler);
})();
```

---

### Form Validation

1. `Disabling Browser Validation (novalidate attribute)`:
   You can turn off the browser’s built-in validation by adding the novalidate attribute to the `form` This allows you to fully control validation using JavaScript or a custom library, rather than relying on automatic checks.

2. `HTML5 Validation Attributes` :
   HTML provides built-in validation through attributes like required, minlength, maxlength, min, max, pattern, and type. These attributes make it easy to add basic validation rules directly in the HTML without writing JavaScript.

3. `Constraint Validation API (JavaScript-based control)`:
   The Constraint Validation API lets you programmatically check and customize form validation in JavaScript. It provides methods like checkValidity() and setCustomValidity(), and properties like validity and validationMessage, allowing you to display custom messages, check specific errors, and control when and how a form submits.

---

```js
// Import the necessary handler
import { todoSubmitHandler } from "./src/submitHandler.js";

// Select the form and input elements
let todoForm = document.querySelector("#todoForm");
let todoList = document.querySelector("#todoList");
const todoInput = todoForm.querySelector("#todo"); // Assuming there's an input with id 'todo'

// ✅ Add form submission event listener with validation
if (todoForm) {
  todoForm.addEventListener("submit", (e) => {
    e.preventDefault(); // Prevent form from submitting immediately

    // Form validation
    if (!todoInput.value.trim()) {
      // Check if the input is empty or just spaces
      alert("Please enter a todo task!");
      todoInput.focus(); // Optionally focus on the input field
      return; // Exit if validation fails
    }

    // If valid, proceed to submit
    todoSubmitHandler(e, todoForm, todoList);
  });
} else {
  console.warn("#todoForm element not found");
}
```

---

### Form Data
FormData is a JavaScript object that lets you easily collect and work with form data, especially for sending it with fetch() or XMLHttpRequest. It grabs form input values as key-value pairs.


```html
<form id="myForm">
  <input type="text" name="username" placeholder="Username" />
  <input type="email" name="email" placeholder="Email" />
  <button type="submit">Submit</button>
</form>

<script>
  const form = document.getElementById('myForm')

  form.addEventListener('submit', function (event) {
    event.preventDefault() // prevent form from submitting normally

    const formData = new FormData(form)

    for (const [key, value] of formData.entries()) {
      console.log(`${key}: ${value}`)
    }

    // You could also send formData using fetch()
    // fetch('/submit', { method: 'POST', body: formData })
  })
</script>
```

---

### event.preventDefault() role in the todo app

event.preventDefault() stops the browser’s default behavior when an event occurs.
In a todo app, you’re using a form to allow the user to add a new task, something like this

```html
<form id="todo-form">
  <input type="text" id="todo-input" placeholder="Add a new task" />
  <button type="submit">Add</button>
</form>
<ul id="todo-list"></ul>
```

Normally, when you click the submit button or press Enter inside the form, the browser submits the form and reloads the page (this is the default behavior for HTML forms).

But in a todo app, you don’t want the page to reload—you just want to add the task dynamically with JavaScript.

That’s where event.preventDefault() comes in. You call it inside the event handler for the form’s submit event to stop the form from reloading the page:

---

```js
const form = document.getElementById("todo-form");
const input = document.getElementById("todo-input");
const list = document.getElementById("todo-list");

form.addEventListener("submit", function (event) {
  event.preventDefault(); // 🚩 stop form from refreshing the page

  const task = input.value.trim();
  if (task !== "") {
    const li = document.createElement("li");
    li.textContent = task;
    list.appendChild(li);
    input.value = ""; // clear input
  }
});
```

Without event.preventDefault(), every time you submit:
✅ The task would get added,
❌ but the page would reload immediately afterward—erasing everything from the DOM.
By preventing the default behavior, you keep everything on the page dynamically updated without a refresh.

In simple terms:
event.preventDefault() stops the page from reloading when the form is submitted, allowing your JavaScript to handle adding the todo item smoothly.

LINK TO THE REPO CREATED BY THE INSTRUCTOR
https://github.com/Oluwasetemi/todo-js-app


