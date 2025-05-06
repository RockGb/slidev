
# Month 2 Week 4

## Arrow Functions in JavaScript

An arrow function is a shorter way to write function expressions introduced in ES6.

### Traditional Function
```js
function add(a, b) {
  return a + b;
}
```

### Arrow Function
```js
const add = (a, b) => a + b;
```

---

## Key Features of Arrow Functions

### 1. Concise Syntax
Arrow functions can be written in one line for simple operations.

```js
const greet = name => `Hello, ${name}`;
```

- If only one parameter: no need for `()`
- If more than one: wrap them in `()`
- If body has only one expression: no `{}` or `return` needed

---

### 2. No `this` Binding
Arrow functions inherit `this` from their lexical context.

```js
function Person() {
  this.age = 0;

  setInterval(() => {
    this.age++;
    console.log(this.age); // `this` refers to Person
  }, 1000);
}
new Person();
```

A regular function would lose the correct `this`.

---

### 3. Cannot Be Used as Constructors

```js
const User = () => {};
const u = new User(); // TypeError
```

---

### 4. No `arguments` Object

```js
const test = () => {
  console.log(arguments); // ReferenceError
};
```

Instead, use rest parameters:

```js
const test = (...args) => {
  console.log(args); // OK
};
```

---

### 5. No `super` Binding
Avoid using arrow functions for class methods that rely on `super`.

---

## Examples

### Multi-line Arrow Function

```js
const multiply = (a, b) => {
  const result = a * b;
  return result;
};
```

### Returning an Object

Wrap the object in parentheses:

```js
const getUser = () => ({ name: 'ojo', role: 'instructor' });
```

---

## Ways to Create Event Listeners in JavaScript

### 1. HTML Inline Event

```html
<button onclick="alert('Clicked!')">Click me</button>
```

### 2. DOM Element Property

```js
const btn = document.getElementById('myBtn');
btn.onclick = () => {
  alert('Clicked!');
};
```

### 3. `addEventListener` Method (Preferred)

```js
const btn = document.getElementById('myBtn');
btn.addEventListener('click', () => {
  alert('Clicked!');
});
```

You can remove it with `removeEventListener`.

---

## Converting Between Objects and Arrays

### Object → Array

```js
const user = { name: "Alex", age: 25 };
```

- `Object.keys(obj)` → `["name", "age"]`
- `Object.values(obj)` → `["Alex", 25]`
- `Object.entries(obj)` → `[["name", "Alex"], ["age", 25]]`

### Array → Object

```js
const entries = [["name", "Alex"], ["age", 25]];
const obj = Object.fromEntries(entries);
console.log(obj); // { name: "Alex", age: 25 }
```

You can also use `reduce()` for custom transformations.

---

## How to Call a Function in JavaScript

### Basic Function Call

```js
function greet(name) {
  console.log("Hello, " + name);
}
greet("Sam"); // Hello, Sam
```

### Arrow Function Call

```js
const add = (a, b) => a + b;
console.log(add(2, 3)); // 5
```

### Calling with Arguments

```js
function sum(x, y) {
  return x + y;
}
let result = sum(4, 5); // result = 9
```

---

## Objects Have 3 Behaviors

When defining properties using `Object.defineProperty`, you can set:

### 1. Enumerable

```js
Object.defineProperty(obj, 'name', {
  value: 'Alex',
  enumerable: true
});
```

### 2. Configurable

```js
Object.defineProperty(obj, 'name', {
  configurable: true
});
```

### 3. Writable

```js
Object.defineProperty(obj, 'name', {
  writable: true
});
```

You can check these using:

```js
console.log(Object.getOwnPropertyDescriptor(obj, 'name'));
```

---

## When to Use Arrow Functions

- Short callbacks  
- Functional programming  
- Preserving `this` (e.g., in React)
