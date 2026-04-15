---
# 🧠 1. `useState` Hook (Core of React)

## 🔹 What is `useState`?

In React, components are **dynamic**—they can change over time.

👉 `useState` is a **Hook** that lets you add **state (memory)** to a functional component.

Without state → UI is static
With state → UI updates dynamically
---

## 🔹 Syntax

```jsx
import { useState } from "react";

const [state, setState] = useState(initialValue);
```

### Breakdown:

- `state` → current value
- `setState` → function to update it
- `initialValue` → starting value

---

## 🔹 Example 1: Basic Counter

```jsx
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h2>Count: {count}</h2>

      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default Counter;
```

---

## 🔹 How it works internally (important)

1. Component renders
2. `useState(0)` → initializes `count = 0`
3. When button clicked:

   ```js
   setCount(count + 1);
   ```

4. React:
   - Updates state
   - Re-renders component
   - UI updates automatically

👉 This is called **Reactive UI**

---

## 🔹 Rules of `useState` (VERY IMPORTANT ⚠️)

1. ❌ Don’t use inside loops/conditions
2. ✅ Always use at top of component
3. ❌ Don’t modify state directly
4. ✅ Always use setter function

### ❌ Wrong:

```js
count = count + 1;
```

### ✅ Correct:

```js
setCount(count + 1);
```

---

## 🔹 Updating State Based on Previous State

Sometimes state updates depend on previous value:

### ❌ Risky:

```js
setCount(count + 1);
```

### ✅ Correct:

```js
setCount((prev) => prev + 1);
```

👉 This avoids bugs when React batches updates

---

## 🔹 Multiple States

```jsx
const [name, setName] = useState("Prakash");
const [age, setAge] = useState(25);
```

👉 You can use multiple `useState` hooks

---

## 🔹 State with Objects

```jsx
const [user, setUser] = useState({
  name: "Prakash",
  age: 25,
});
```

### Update carefully:

```jsx
setUser({
  ...user,
  age: 26,
});
```

👉 Always use **spread operator** to avoid losing data

---

## 🔹 State with Arrays

```jsx
const [items, setItems] = useState([]);
```

### Add item:

```js
setItems([...items, "New Item"]);
```

---

## 🔹 Key Concept

👉 React does NOT track variable changes
👉 It only reacts to **state changes**

---

## 🔹 Common Beginner Mistakes

❌ Forgetting `useState` import
❌ Mutating state directly
❌ Expecting immediate update (state is async)

---

## 🧪 Practice Tasks (Do this now)

### Task 1:

Create a component:

- Button → "Increase Age"
- Initial age = 20
- Increase by 1

---

### Task 2:

Create:

- Input field
- Show typed text below

(Hint: use `useState`)

---

### Task 3:

Create:

- Button → Toggle "ON / OFF"

---

## 🚀 Mini Challenge (Important)

Build this:

```text
Count: 0

[ + ] [ - ] [ Reset ]
```

---
