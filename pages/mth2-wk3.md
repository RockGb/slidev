---
layout: center
transition: fade-out
---

# [Month 2 Week 3]{.gradient-text}

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

## [📦 Bundlers (Vite) and Todo App PR Review]{.text-teal-400}

<br>

### Summary:

#### 1. Bundlers Overview
Browsers have limitations; bundlers help manage modern JavaScript features and dependencies.

**Common bundlers:** Browserify, Webpack, Parcel, Vite

**Benefits of bundlers:**

- Lazy loading (only load code when needed)
- Dynamic imports for better performance

---

#### 2. Focus on Vite

Vite is a modern and fast bundler optimized for speed and simplicity.

#### 3. Creating a Vite Project

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

**Set up build scripts in `package.json`:**

```json
"scripts": {
  "dev": "vite",
  "build": "vite build",
  "preview": "vite preview"
}
```

**Start the development server:**

```bash
npm run dev
```

_You can use_ **`pnpm`** _instead of_ **`npm`** _to initialize and install dependencies._

**Shortcut method: Creating a Vite Project**

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


```bash
npm install
```

```bash
npm run dev
```

#### 4. Pull Request Review – To-do App (Mariam’s Branch)

<br>
- We cloned and checked out Mariam’s `vite` branch.
- Added `.gitignore` to exclude `node_modules` and other unnecessary files from version control.
- To list all files (including hidden ones like `.git`):

```bash
ls -la
```

<br>

#### Contributions

- Mariam:
  - Modularized the project structure
  - Enabled double-click to edit feature
  - Implemented `localStorage` saving
-  Osawawo:
   - Added checkbox functionality