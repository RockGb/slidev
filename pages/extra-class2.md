---
layout: center
transition: fade-out
---

# [Extra Class Week 2]{.gradient-text}

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

## [⚛️ React in Vanilla Projects]{.text-teal-400}

<br>

### Libraries vs Frameworks

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

## React Setup & Vite

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

### React DOM Methods & Components

### Creating React Elements

```js
const nemElement = React.createElement("h1", null, "I am a new element");
console.log(nemElement); // Logs a React object, not HTML
```

### Rendering Elements

```js
const rootElement = document.querySelector("#app");
const root = ReactDOM.createRoot(rootElement);
root.render(nemElement);
```

### Creating Components

```js
function App() {
  return React.createElement("div", null, "This is a React Component");
}

const root = ReactDOM.createRoot(document.querySelector("#app"));
root.render(React.createElement(App));
```

---

### React State

```js
const [todos, setTodos] = React.useState([]);
// Default values: [], '', null, 0
```

- useState returns a pair `[state, setState]`
- Individual logic placed in **handlers**


