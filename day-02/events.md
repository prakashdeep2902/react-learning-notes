# ⚡ 2. Event Handling in React (onClick, onChange)

This is where your app becomes **interactive**.

---

## 🔹 What is Event Handling?

👉 Event handling means **responding to user actions**

Examples:

- Clicking a button
- Typing in an input
- Submitting a form

In React, events are written using **camelCase**

---

## 🔹 Basic Syntax

```jsx
<button onClick={handleClick}>Click Me</button>
```

👉 You pass a **function reference**, not call it directly.

---

## 🔹 Example 1: onClick Event

```jsx
import React from "react";

function App() {
  const handleClick = () => {
    alert("Button Clicked!");
  };

  return <button onClick={handleClick}>Click Me</button>;
}

export default App;
```

---

## 🔹 Passing Function Inline

```jsx
<button onClick={() => console.log("Clicked")}>Click</button>
```

---

## 🔹 ❌ Common Mistake

```jsx
<button onClick={handleClick()}>
```

👉 This will run immediately on render (WRONG)

---

## 🔹 Example 2: Using State + onClick

```jsx
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h2>{count}</h2>

      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

👉 This is how events + state work together

---

# 🔹 onChange Event (Very Important)

Used with:

- Input fields
- Textarea
- Select

---

## 🔹 Example: Input Handling

```jsx
import React, { useState } from "react";

function InputExample() {
  const [name, setName] = useState("");

  return (
    <div>
      <input
        type="text"
        value={name}
        onChange={(e) => setName(e.target.value)}
      />

      <p>You typed: {name}</p>
    </div>
  );
}
```

---

## 🔹 Understanding `e` (Event Object)

```js
onChange={(e) => console.log(e)}
```

👉 `e.target.value` → current input value

---

## 🔹 Controlled Components (Important Concept)

👉 React controls the input value

```jsx
<input value={state} onChange={...} />
```

✔ Single source of truth
✔ Easier validation
✔ Predictable UI

---

## 🔹 Example: Multiple Inputs

```jsx
const [form, setForm] = useState({
  name: "",
  email: "",
});

<input
  name="name"
  onChange={(e) => setForm({ ...form, [e.target.name]: e.target.value })}
/>;
```

---

## 🔹 Other Common Events

- `onSubmit`
- `onMouseEnter`
- `onMouseLeave`
- `onKeyDown`

---

## 🔹 Example: Form Submit

```jsx
function Form() {
  const handleSubmit = (e) => {
    e.preventDefault(); // stop reload
    alert("Form Submitted");
  };

  return (
    <form onSubmit={handleSubmit}>
      <button type="submit">Submit</button>
    </form>
  );
}
```

---

## 🔹 Key Concepts to Remember

✔ Events are camelCase
✔ Pass function reference
✔ Use `e.target.value`
✔ Combine with state

---

## 🧪 Practice Tasks

### Task 1:

- Button → Show alert "Hello Prakash"

---

### Task 2:

- Input field
- Show live typing below

---

### Task 3:

- Button → Increase count
- Button → Decrease count

---

### Task 4:

Create a form:

- Name input
- Email input
- Submit button
- Console log data

---

## 🚀 Mini Challenge

Build this:

```text
Enter Name: [_____]

[Show Name]

Output: Hello, Prakash
```

---
