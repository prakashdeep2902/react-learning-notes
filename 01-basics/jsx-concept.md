# 🔥 What is JSX?

👉 JSX = **JavaScript XML**

It lets you write **HTML-like code inside JavaScript**.

```jsx
const element = <h1>Hello Prakash</h1>;
```

👉 Behind the scenes:

```js
React.createElement("h1", null, "Hello Prakash");
```

---

# 🧠 Why JSX?

Without JSX:

```js
React.createElement("h1", null, "Hello");
```

With JSX:

```jsx
<h1>Hello</h1>
```

👉 Cleaner, readable, faster to write

---

# 📜 JSX RULES (VERY IMPORTANT 🔥)

---

## ✅ Rule 1: Must Return a Single Parent Element

❌ Wrong:

```jsx
return (
  <h1>Hello</h1>
  <p>Welcome</p>
);
```

✅ Correct:

```jsx
return (
  <div>
    <h1>Hello</h1>
    <p>Welcome</p>
  </div>
);
```

👉 OR use Fragment:

```jsx
<>
  <h1>Hello</h1>
  <p>Welcome</p>
</>
```

---

## ✅ Rule 2: Use `className` instead of `class`

❌

```jsx
<div class="box"></div>
```

✅

```jsx
<div className="box"></div>
```

---

## ✅ Rule 3: Use `{}` for JavaScript

```jsx
const name = "Prakash";

return <h1>Hello {name}</h1>;
```

---

## ✅ Rule 4: Self-closing Tags Required

❌

```jsx
<img src="img.png">
```

✅

```jsx
<img src="img.png" />
```

---

## ✅ Rule 5: Inline Styles are Objects

❌

```jsx
<h1 style="color: red"></h1>
```

✅

```jsx
<h1 style={{ color: "red" }}>Hello</h1>
```

---

## ✅ Rule 6: Use camelCase for attributes

❌

```jsx
<button onclick="handleClick()"></button>
```

✅

```jsx
<button onClick={handleClick}></button>
```

---

# ⚡ JSX WITH EXPRESSIONS

You can use ANY JavaScript inside `{}`

---

## 👉 Variables

```jsx
const age = 25;

<p>Age: {age}</p>;
```

---

## 👉 Functions

```jsx
function greet() {
  return "Hello";
}

<h1>{greet()}</h1>;
```

---

## 👉 Math / Logic

```jsx
<p>{10 + 5}</p>
```

---

# 🔀 CONDITIONAL RENDERING IN JSX

---

## ✅ Using Ternary Operator

```jsx
const isLoggedIn = true;

return <h1>{isLoggedIn ? "Welcome" : "Please Login"}</h1>;
```

---

## ✅ Using &&

```jsx
const show = true;

return <div>{show && <p>This is visible</p>}</div>;
```

---

# 🔁 RENDERING LISTS

```jsx
const users = ["Prakash", "Rahul", "Amit"];

return (
  <ul>
    {users.map((user, index) => (
      <li key={index}>{user}</li>
    ))}
  </ul>
);
```

👉 `key` is IMPORTANT in lists

---

# 🎯 JSX WITH COMPONENTS

```jsx
function Hello() {
  return <h1>Hello World</h1>;
}

function App() {
  return <Hello />;
}
```

---

# 🧱 FULL EXAMPLE (REALISTIC)

```jsx
function App() {
  const user = "Prakash";
  const isLoggedIn = true;

  return (
    <div>
      <h1>Hello {user}</h1>

      {isLoggedIn ? <p>Welcome back!</p> : <p>Please login</p>}

      <img src="https://via.placeholder.com/150" />

      <button onClick={() => alert("Clicked!")}>Click Me</button>
    </div>
  );
}
```

---

# ⚠️ COMMON MISTAKES (VERY IMPORTANT)

- ❌ Forgetting `{}` for JS
- ❌ Using `class` instead of `className`
- ❌ Not closing tags
- ❌ Returning multiple elements without wrapper
- ❌ Using normal HTML event names (`onclick`)

---

# 🧠 HOW TO THINK IN JSX

👉 Think like this:

> "I am writing UI that reacts to data"

Example:

```jsx
<h1>Hello {user}</h1>
```

UI changes when `user` changes

---

# 📝 WHAT TO WRITE IN YOUR `jsx.md`

Include:

- Definition of JSX
- All rules
- 3–4 examples
- Common mistakes
- Your understanding

---

# 💥 YOUR TASK (IMPORTANT)

👉 Practice these:

1. Show your name using JSX
2. Show age using `{}`
3. Add image
4. Add button with click alert
5. Show message using condition
