Great progress 🔥 Day 4 is where React starts feeling _real-world useful_. You’ll now connect your UI with APIs and handle async data properly.

---

# 📅 **Day 04 – API Integration in React**

## 🎯 Goal of Day 04

By the end of today, you should be able to:

- Fetch data from an API
- Use `useEffect` properly
- Handle loading & error states
- Use both **Fetch API** and **Axios**

---

# 🧠 1. Understand `useEffect` (Core Concept)

### 👉 Why we need it?

React components re-render often. But API calls should:

- Run **only once on mount**
- Or run when **dependency changes**

---

### ✅ Basic Syntax

```js
import { useEffect } from "react";

useEffect(() => {
  console.log("Component mounted");
}, []);
```

👉 `[]` = run only once (componentDidMount)

---

### 🔁 With Dependency

```js
useEffect(() => {
  console.log("Runs when count changes");
}, [count]);
```

---

### ❗ Important Rules

- Never make `useEffect` callback async directly ❌
- Always use async function inside it ✅

```js
useEffect(() => {
  const fetchData = async () => {
    // API call
  };

  fetchData();
}, []);
```

---

# 🌐 2. Fetch API (Native JS)

## ✅ Example: Fetch Users

```js
import { useEffect, useState } from "react";

function Users() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/users")
      .then((res) => res.json())
      .then((data) => setUsers(data));
  }, []);

  return (
    <div>
      {users.map((user) => (
        <p key={user.id}>{user.name}</p>
      ))}
    </div>
  );
}
```

---

# 📦 3. Axios (Better Alternative)

## 👉 Install

```bash
npm install axios
```

---

## ✅ Example with Axios

```js
import axios from "axios";
import { useEffect, useState } from "react";

function Users() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    const getUsers = async () => {
      const res = await axios.get("https://jsonplaceholder.typicode.com/users");
      setUsers(res.data);
    };

    getUsers();
  }, []);

  return (
    <div>
      {users.map((user) => (
        <p key={user.id}>{user.name}</p>
      ))}
    </div>
  );
}
```

---

# ⚖️ Fetch vs Axios

| Feature        | Fetch API | Axios  |
| -------------- | --------- | ------ |
| Built-in       | ✅ Yes    | ❌ No  |
| JSON handling  | Manual    | Auto   |
| Error handling | Weak      | Better |
| Interceptors   | ❌        | ✅     |

👉 **Use Axios in real projects**

---

# ⏳ 4. Handle Loading & Error States (VERY IMPORTANT)

## ✅ Real-world example

```js
import axios from "axios";
import { useEffect, useState } from "react";

function Users() {
  const [users, setUsers] = useState([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    const fetchUsers = async () => {
      try {
        const res = await axios.get(
          "https://jsonplaceholder.typicode.com/users",
        );
        setUsers(res.data);
      } catch (err) {
        setError("Something went wrong!");
      } finally {
        setLoading(false);
      }
    };

    fetchUsers();
  }, []);

  if (loading) return <p>Loading...</p>;
  if (error) return <p>{error}</p>;

  return (
    <div>
      {users.map((user) => (
        <p key={user.id}>{user.name}</p>
      ))}
    </div>
  );
}
```

---

# 🧪 5. Practice Tasks (IMPORTANT)

## 🟢 Task 1 (Easy)

- Fetch posts from:

```
https://jsonplaceholder.typicode.com/posts
```

- Display:
  - title
  - body

---

## 🟡 Task 2 (Medium)

- Add:
  - Loading spinner/text
  - Error handling

- Show:
  - "No data found" if empty

---

## 🔴 Task 3 (Advanced)

- Add button: **"Reload Data"**
- Add search filter:
  - Filter posts by title

---

## 🔥 Bonus Task (Real Dev Level)

Create:
👉 `UserList` component
👉 `UserCard` component

Pass data using props (revision of Day 3)

---

# 🧠 Key Takeaways

- `useEffect` = side effects (API calls)
- Always handle:
  - loading
  - error

- Axios > Fetch in real apps
- Keep API logic clean & reusable

---

# 📁 Suggested Folder Structure (Update)

```
src/
 ├── components/
 │    ├── UserList.js
 │    ├── UserCard.js
 ├── services/
 │    ├── api.js   👈 (Axios config here)
 ├── App.js
```

---

# 🚀 Tomorrow Preview (Day 05)

- Forms in React
- Controlled components
- Handling user input
- Validation

---

If you want, I can:
✅ Give you **tracker.md updated till Day 04**
✅ Review your code
✅ Give you a **mini project (API-based app)**

Just tell me 👍
