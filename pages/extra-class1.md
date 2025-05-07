---
layout: center
transition: fade-out
---

# [Extra Class Week 1]{.gradient-text}

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

## [🧱 Modules and Modularity]{.text-teal-400}

<br>

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

### 2. Bundlers

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

### 3. Imports and Exports

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