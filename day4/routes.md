# 📘 Day 5 – React Routing + Material UI (Notes)

---

## 🚀 1. Install Required Packages

```bash
npm install react-router-dom
npm install @mui/material @emotion/react @emotion/styled
npm install @mui/icons-material
```

---

## 🧠 2. React Router Basics

### Wrap App with BrowserRouter

```jsx
import { BrowserRouter } from "react-router-dom";

<BrowserRouter>
  <App />
</BrowserRouter>;
```

---

## 🔀 3. Define Routes

```jsx
import { Routes, Route } from "react-router-dom";

<Routes>
  <Route path="/" element={<Home />} />
  <Route path="/about" element={<About />} />
</Routes>;
```

---

## 🔗 4. Navigation

```jsx
import { Link } from "react-router-dom";

<Link to="/">Home</Link>;
```

❌ Avoid using `<a>` (causes page reload)

---

## 🔄 5. Dynamic Routing

```jsx
<Route path="/user/:id" element={<User />} />
```

### Access Params

```jsx
import { useParams } from "react-router-dom";

const { id } = useParams();
```

---

## 🧭 6. Programmatic Navigation

```jsx
import { useNavigate } from "react-router-dom";

const navigate = useNavigate();
navigate("/home");
```

---

## 🧱 7. Passing Data in onClick

### ❌ Wrong

```jsx
onClick={handleClick(id)}
```

### ✅ Correct

```jsx
onClick={() => handleClick(id)}
```

---

## 🧾 8. Example (Card Click with ID)

```jsx
onClick={() => HandelCardClick(value.id)}
```

```jsx
const HandelCardClick = (id) => {
  console.log(id);
};
```

---

## 🎨 9. Material UI Basics

### Import Components

```jsx
import { Button, TextField, Card } from "@mui/material";
```

---

## 🧾 10. Material UI Form Example

```jsx
import { TextField, Button } from "@mui/material";
import { useState } from "react";

const [title, setTitle] = useState("");

<TextField
  label="Title"
  value={title}
  onChange={(e) => setTitle(e.target.value)}
/>

<Button variant="contained">Submit</Button>
```

---

## 🏗️ 11. Blog App Structure

```
src/
├── components/
│   └── Navbar.jsx
├── pages/
│   ├── Home.jsx
│   ├── BlogDetail.jsx
│   ├── CreatePost.jsx
├── App.jsx
```

---

## ⚠️ Common Mistakes

- Forgetting BrowserRouter
- Using `<a>` instead of `<Link>`
- Calling function instead of passing function
- Wrong route paths

---

## 🎯 Key Takeaways

- React Router enables SPA navigation
- Use dynamic routes for IDs
- Use Material UI for fast UI development
- Always pass arguments using arrow functions in events

---

## 🧪 Practice Tasks

1. Create 3 pages (Home, About, Contact)
2. Add dynamic route `/post/:id`
3. Build blog UI with Material UI
4. Add navigation and form

---

🔥 Next Step: Forms + State Management (Day 6)
