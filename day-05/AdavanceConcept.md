# 🚀 Day 6 – Advanced React Concepts

---

# 1️⃣ useEffect (Deep Dive)

## 🔹 What is useEffect?

`useEffect` lets you **run side effects** in your component.

👉 Side effects = things like:

- API calls
- timers
- DOM updates
- subscriptions

---

## 🔹 Basic Syntax

```js
useEffect(() => {
  // side effect code
}, []);
```

---

## 🔹 Case 1: Run only once (on mount)

```js
import { useEffect } from "react";

function App() {
  useEffect(() => {
    console.log("Component mounted");
  }, []);

  return <h1>Hello</h1>;
}
```

👉 `[]` = run only once

---

## 🔹 Case 2: Run when state changes

```js
const [count, setCount] = useState(0);

useEffect(() => {
  console.log("Count changed:", count);
}, [count]);
```

👉 Runs whenever `count` changes

---

## 🔹 Case 3: Cleanup function

```js
useEffect(() => {
  const interval = setInterval(() => {
    console.log("Running...");
  }, 1000);

  return () => {
    clearInterval(interval);
    console.log("Cleanup done");
  };
}, []);
```

👉 Cleanup runs when:

- component unmounts
- before next effect runs

---

## 🔥 Common Mistakes

❌ Infinite loop:

```js
useEffect(() => {
  setCount(count + 1);
});
```

👉 No dependency array → runs forever

---

## ✅ Practice Task

👉 Create:

- Counter
- Log "Updated" every time count changes
- Add cleanup log

---

# 2️⃣ useRef (Basics)

## 🔹 What is useRef?

`useRef` is used to:

1. Access DOM elements
2. Store values **without re-render**

---

## 🔹 Example 1: Access input

```js
import { useRef } from "react";

function App() {
  const inputRef = useRef();

  const focusInput = () => {
    inputRef.current.focus();
  };

  return (
    <>
      <input ref={inputRef} />
      <button onClick={focusInput}>Focus</button>
    </>
  );
}
```

---

## 🔹 Example 2: Store value without re-render

```js
const countRef = useRef(0);

const handleClick = () => {
  countRef.current++;
  console.log(countRef.current);
};
```

👉 UI will NOT update (no re-render)

---

## 🔥 Difference

| Hook     | Causes re-render? |
| -------- | ----------------- |
| useState | ✅ Yes            |
| useRef   | ❌ No             |

---

## ✅ Practice Task

👉 Build:

- Input field
- Button → focus input
- Track clicks using `useRef`

---

# 3️⃣ Lifting State Up

## 🔹 Problem

Two components need same data.

👉 Example:

- Search input
- Product list

---

## ❌ Wrong way

Each component has its own state

---

## ✅ Correct way (Lift State Up)

Move state to parent.

---

## 🔹 Example

```js
function Parent() {
  const [text, setText] = useState("");

  return (
    <>
      <ChildInput setText={setText} />
      <ChildDisplay text={text} />
    </>
  );
}
```

---

### Child 1

```js
function ChildInput({ setText }) {
  return <input onChange={(e) => setText(e.target.value)} />;
}
```

---

### Child 2

```js
function ChildDisplay({ text }) {
  return <h2>{text}</h2>;
}
```

---

## 🔥 Key Idea

👉 **Single source of truth**

---

## ✅ Practice Task

👉 Build:

- Input component
- Preview component
- Share data via parent

---

# 4️⃣ Reusable Components

## 🔹 What is it?

Write once → use everywhere

---

## 🔹 Example: Button Component

```js
function Button({ label, onClick }) {
  return <button onClick={onClick}>{label}</button>;
}
```

---

## 🔹 Usage

```js
<Button label="Save" onClick={handleSave} />
<Button label="Delete" onClick={handleDelete} />
```

---

## 🔥 Best Practices

- Use props
- Keep generic
- Avoid hardcoding

---

## ✅ Practice Task

👉 Create:

- Card component
- Pass title + description
- Reuse 3 times

---

# 5️⃣ Build Project: Search / Filter App 🔥

Now combine everything.

---

## 🔹 Step 1: Data

```js
const items = ["Apple", "Banana", "Mango", "Orange"];
```

---

## 🔹 Step 2: Parent

```js
function App() {
  const [search, setSearch] = useState("");

  const filteredItems = items.filter((item) =>
    item.toLowerCase().includes(search.toLowerCase()),
  );

  return (
    <>
      <Search setSearch={setSearch} />
      <List items={filteredItems} />
    </>
  );
}
```

---

## 🔹 Search Component

```js
function Search({ setSearch }) {
  return (
    <input
      placeholder="Search..."
      onChange={(e) => setSearch(e.target.value)}
    />
  );
}
```

---

## 🔹 List Component

```js
function List({ items }) {
  return (
    <ul>
      {items.map((item, index) => (
        <li key={index}>{item}</li>
      ))}
    </ul>
  );
}
```

---

## 🔥 Concepts Used

✔ Lifting state
✔ Reusable components
✔ Filtering logic
✔ Props

---

## 🚀 Bonus (Advanced)

Add:

- `useEffect` → log search
- `useRef` → auto-focus input

---

# 6️⃣ Push Notes to GitHub

## 🔹 What to include

Create repo: `react-learning-notes`

---

## 📁 Day 6 Structure

```
Day-6/
 ├── useEffect.md
 ├── useRef.md
 ├── lifting-state.md
 ├── reusable-components.md
 ├── project-search-app/
```

---

## 🔹 Commit

```bash
git add .
git commit -m "Day 6 - Advanced React Concepts"
git push
```

---

# 🎯 Final Challenge (DO THIS)

Build this:

✅ Search bar
✅ Auto focus (useRef)
✅ Log search (useEffect)
✅ Reusable list component
✅ Lifted state

---

# 💡 What You Just Learned

- Side effects (useEffect)
- DOM & persistent values (useRef)
- Data flow (lifting state)
- Component design
- Mini real-world app

---
