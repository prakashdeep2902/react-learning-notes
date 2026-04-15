# 🔀 3. Conditional Rendering (Deep Dive)

---

## 🔹 What is Conditional Rendering?

👉 It means **showing different UI based on conditions**

Just like JavaScript:

```js
if (condition) {
  // do something
}
```

In React:
👉 You decide **what to render (show)** based on state/props

---

## 🔹 Why it matters?

Real apps ALWAYS use this:

- Login / Logout UI
- Show loader while fetching data
- Show "No Data Found"
- Toggle components

---

# 🔥 4 Ways to Do Conditional Rendering

---

## 1️⃣ Using `if/else` (outside JSX)

```jsx id="4n7f8a"
function App() {
  const isLoggedIn = true;

  if (isLoggedIn) {
    return <h1>Welcome Prakash</h1>;
  } else {
    return <h1>Please Login</h1>;
  }
}
```

👉 Used when logic is bigger

---

## 2️⃣ Ternary Operator (MOST USED 🔥)

```jsx id="qg7n8p"
{
  condition ? <ComponentA /> : <ComponentB />;
}
```

### Example:

```jsx id="3rj0ak"
const isLoggedIn = false;

return <div>{isLoggedIn ? <h1>Welcome</h1> : <h1>Login</h1>}</div>;
```

---

## 3️⃣ Logical AND (`&&`) (for single condition)

```jsx id="9s3fla"
{
  condition && <Component />;
}
```

### Example:

```jsx id="f6x92d"
const showMessage = true;

return <div>{showMessage && <p>This is visible</p>}</div>;
```

👉 If `true` → shows
👉 If `false` → nothing

---

## 4️⃣ Switch / Multiple Conditions

```jsx id="7m92df"
switch (status) {
  case "loading":
    return <h1>Loading...</h1>;
  case "success":
    return <h1>Data Loaded</h1>;
  case "error":
    return <h1>Error</h1>;
}
```

---

# 🔹 Real Example (VERY IMPORTANT)

## Toggle Login Button

```jsx id="4h3kdf"
import React, { useState } from "react";

function App() {
  const [isLoggedIn, setIsLoggedIn] = useState(false);

  return (
    <div>
      <h2>{isLoggedIn ? "Welcome Prakash" : "Please Login"}</h2>

      <button onClick={() => setIsLoggedIn(!isLoggedIn)}>
        {isLoggedIn ? "Logout" : "Login"}
      </button>
    </div>
  );
}
```

---

# 🔹 Multiple Conditions Example

```jsx id="2p9kfd"
const age = 20;

return (
  <div>
    {age < 18 ? <h1>Minor</h1> : age < 60 ? <h1>Adult</h1> : <h1>Senior</h1>}
  </div>
);
```

---

# ❗ Common Mistakes

❌ Using `if` directly inside JSX

```jsx
{
  if (true) {
    return <h1>Hello</h1>;
  }
}
```

👉 ❌ This will break

---

✔ Correct way:

- Use ternary
- Use `&&`
- Or move logic outside JSX

---

# 🧠 Pro Tips

✔ Keep JSX clean
✔ Avoid nested ternary (hard to read)
✔ Use variables for clarity

---

# 🧪 Practice Tasks

### Task 1:

- Show "Online" / "Offline"
- Toggle using button

---

### Task 2:

- Input field
- If empty → show "Please enter name"
- Else → show "Hello {name}"

---

### Task 3:

- Show loader:

```text
Loading...
```

After 2 seconds → show "Data Loaded"

---

# 🚀 Mini Challenge

Build this:

```text
[Login Button]

If clicked:
→ Show Dashboard
Else:
→ Show Login Message
```

---

## 🔥 Real-World Thinking

👉 Conditional rendering = **UI logic**

You control:

- what user sees
- when they see it
- based on state

---
