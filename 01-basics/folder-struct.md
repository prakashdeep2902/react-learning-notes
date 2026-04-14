# 📂 React Folder Structure (Vite Project)

When you create a project using Vite, you’ll see something like:

```
my-app/
│
├── node_modules/
├── public/
├── src/
│   ├── assets/
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
│
├── index.html
├── package.json
└── vite.config.js
```

---

# 🧠 Understand Each Folder/File

---

## 📁 1. `node_modules/`

- Contains all installed packages
- Created automatically

👉 Ignore this folder (never edit manually)

---

## 📁 2. `public/`

- Static files (images, icons, etc.)
- Directly served

Example:

```
public/logo.png
```

Use:

```jsx
<img src="/logo.png" />
```

---

## 📁 3. `src/` ⭐ (MOST IMPORTANT)

👉 This is where **you will work 90% of the time**

---

### 📄 `main.jsx` (Entry Point)

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";

ReactDOM.createRoot(document.getElementById("root")).render(<App />);
```

👉 Flow:

```
main.jsx → App.jsx → Your Components
```

---

### 📄 `App.jsx` (Main Component)

```jsx
function App() {
  return <h1>Hello React</h1>;
}

export default App;
```

👉 This is your **main UI container**

---

### 📁 `assets/`

- Store images, icons, etc.

---

### 📄 `index.css`

- Global styles

---

# 🌐 4. `index.html`

```html
<div id="root"></div>
```

👉 React injects your app here

---

# ⚙️ 5. `package.json`

- Project info
- Dependencies
- Scripts

Example:

```json
"scripts": {
  "dev": "vite",
  "build": "vite build"
}
```

---

# 🔧 6. `vite.config.js`

- Configuration file for Vite
- Ignore for now (Day 1)

---

# 🔥 REAL FLOW (IMPORTANT)

```
index.html
   ↓
main.jsx
   ↓
App.jsx
   ↓
Components
```

---

# 💡 How YOU Should Organize (From Day 1)

Inside `src/`, start creating your own folders:

```
src/
│
├── components/
│   └── ProfileCard.jsx
│
├── App.jsx
├── main.jsx
```

---

# 🧱 Example: Component File

```jsx
// src/components/ProfileCard.jsx

function ProfileCard({ name }) {
  return <h2>{name}</h2>;
}

export default ProfileCard;
```

Use in `App.jsx`:

```jsx
import ProfileCard from "./components/ProfileCard";

function App() {
  return <ProfileCard name="Prakash" />;
}
```

---

# ⚠️ Beginner Mistakes

- ❌ Writing everything in App.jsx
- ❌ Not creating components folder
- ❌ Confusing public vs src
- ❌ Editing node_modules

---

# 🎯 What You Should Do Now

👉 After reading this:

1. Create a React app
2. Open folder structure
3. Create:

   ```
   src/components/ProfileCard.jsx
   ```

4. Import it into App.jsx
5. Run app

---

# 💥 Simple Way to Remember

👉 Think like this:

- `index.html` → container
- `main.jsx` → entry
- `App.jsx` → root UI
- `components/` → building blocks
