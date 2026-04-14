# 📘 Day 1 – React Basics + Setup with Vite

## 🔹 1. What is React?

**React** is a **JavaScript library** used to build **user interfaces (UI)** — especially for **single-page applications (SPAs)**.

### 👉 In simple words:

React helps you build **interactive websites** by breaking UI into **small reusable pieces (components)**.

---

## 🔹 Key Concepts

### ✅ 1. Component-Based Architecture

- UI is divided into **components**
- Example:
  - Navbar
  - Button
  - Card

Each component is reusable.

---

### ✅ 2. Virtual DOM

- React uses a **virtual DOM** (a lightweight copy of real DOM)
- It updates only changed parts → **faster performance**

---

### ✅ 3. Declarative UI

- You describe **what UI should look like**
- React handles **how to update it**

---

### ✅ 4. Reusability

- Write once → use multiple times

---

## 🔹 Why React is Popular?

- Fast ⚡
- Reusable components ♻️
- Huge ecosystem 🌍
- Backed by **Meta**

---

# ⚙️ 2. Setup React App using Vite

We use **Vite** because it's:

- Super fast ⚡
- Simple setup
- Modern tooling

---

## 🧰 Step-by-Step Setup

### ✅ Step 1: Create Project

```bash
npm create vite@latest
```

---

### ✅ Step 2: Enter Project Details

You’ll be asked:

- Project name → `react-learning`
- Framework → `React`
- Variant → `JavaScript` (or TypeScript if you want)

---

### ✅ Step 3: Navigate to Project

```bash
cd react-learning
```

---

### ✅ Step 4: Install Dependencies

```bash
npm install
```

---

### ✅ Step 5: Start Development Server

```bash
npm run dev
```

---

### 🌐 Output

You’ll see something like:

```
http://localhost:5173/
```

Open it in browser 🚀

---

## 📁 Project Structure (Important)

```
react-learning/
│
├── index.html
├── package.json
├── vite.config.js
│
└── src/
    ├── main.jsx
    ├── App.jsx
    └── assets/
```

---

### 🔍 Important Files

- `main.jsx` → Entry point
- `App.jsx` → Main component
- `index.html` → Root HTML

---

## 🧠 First React Code Example

```jsx
function App() {
  return <h1>Hello React 🚀</h1>;
}

export default App;
```

---

# 📝 GitHub Notes (You can copy this)

```md
# Day 1 - React Basics

## What is React?

React is a JavaScript library used to build user interfaces using components.

## Key Features

- Component-based architecture
- Virtual DOM
- Declarative UI
- Reusability

## Why React?

- Fast
- Scalable
- Easy to manage UI

## Setup using Vite

1. npm create vite@latest
2. Select React
3. cd project-name
4. npm install
5. npm run dev

## Folder Structure

- main.jsx → entry point
- App.jsx → main component
- index.html → root file
```

---

# ✅ Your Day 1 Goal

✔ Understand what React is
✔ Install React using Vite
✔ Run your first app
✔ Understand folder structure

---

If you want, I can also:

- Give you **Day 1 small practice tasks (important 🔥)**
- Or create your **tracker.md file for GitHub** next

Just tell me 👍
