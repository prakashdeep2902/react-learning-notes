# 📋 4. Lists & Keys (VERY IMPORTANT)

This concept is used in **Todo apps, APIs, dashboards, tables—everywhere**.

---

# 🔹 What are Lists in React?

👉 Rendering multiple items dynamically

Example:

```js
["Apple", "Banana", "Mango"];
```

We want to display them in UI.

---

## 🔹 Basic Example

```jsx id="x9f3k1"
function App() {
  const fruits = ["Apple", "Banana", "Mango"];

  return (
    <ul>
      {fruits.map((fruit) => (
        <li>{fruit}</li>
      ))}
    </ul>
  );
}
```

---

## 🔹 What is `.map()`?

👉 A JavaScript method to loop through arrays

```js id="o2m4k8"
array.map((item, index) => {
  return something;
});
```

👉 In React → we return JSX

---

# ❗ Problem (Important)

If you run the above code, React gives warning:

👉 **"Each child should have a unique key"**

---

# 🔑 What are Keys?

👉 Keys help React identify which items changed, added, or removed

👉 Think of it like:

- Aadhar number for each element 😄

---

## 🔹 Fix with Keys

```jsx id="2p8xq9"
<ul>
  {fruits.map((fruit, index) => (
    <li key={index}>{fruit}</li>
  ))}
</ul>
```

---

## 🔹 Better Way (IMPORTANT)

❌ Avoid using index as key (in dynamic lists)

✔ Use unique ID:

```jsx id="9z4kdp"
const fruits = [
  { id: 1, name: "Apple" },
  { id: 2, name: "Banana" },
];

<ul>
  {fruits.map((fruit) => (
    <li key={fruit.id}>{fruit.name}</li>
  ))}
</ul>;
```

---

# 🔹 Why Keys Matter (Deep Understanding)

React uses **Virtual DOM**

👉 When list changes:

- React compares old vs new list
- Uses keys to optimize updates

Without keys:
❌ Wrong updates
❌ Performance issues

---

# 🔹 Rendering Objects

```jsx id="1k8dfp"
const users = [
  { id: 1, name: "Prakash", age: 25 },
  { id: 2, name: "Rahul", age: 22 },
];

<ul>
  {users.map((user) => (
    <li key={user.id}>
      {user.name} - {user.age}
    </li>
  ))}
</ul>;
```

---

# 🔹 Rendering Components in List

```jsx id="k9d2ls"
function User({ name }) {
  return <h3>{name}</h3>;
}

{
  users.map((user) => <User key={user.id} name={user.name} />);
}
```

---

# 🔹 Filtering + Mapping (Real Use Case)

```jsx id="p3r7lm"
{
  users
    .filter((user) => user.age > 23)
    .map((user) => <p key={user.id}>{user.name}</p>);
}
```

---

# ❗ Common Mistakes

❌ Missing key
❌ Using random values as key
❌ Using index in dynamic lists

---

# 🧠 Pro Tips

✔ Always prefer **unique ID**
✔ Keep keys stable
✔ Don’t generate keys inside render (like `Math.random()`)

---

# 🧪 Practice Tasks

### Task 1:

Render:

```text
["React", "Node", "MongoDB"]
```

---

### Task 2:

Render users:

```js
[
  { id: 1, name: "Prakash" },
  { id: 2, name: "Amit" },
];
```

---

### Task 3:

- Show only even numbers from list

---

### Task 4:

- Input field
- Add items to list
- Display dynamically

👉 (This is basically Todo App base)

---

# 🚀 Mini Challenge

Build:

```text
[Input Field]
[Add Button]

List:
- Task 1
- Task 2
- Task 3
```

---

# 🔥 Real-World Insight

👉 Lists + State = Dynamic Apps

You’ll use this in:

- Todo App ✅
- API Data Rendering ✅
- Tables / Dashboards ✅

---
