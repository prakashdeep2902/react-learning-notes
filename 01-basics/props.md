---
# 📘 React Props – Complete Notes
---

## 📌 1. Definition

**Props (short for “properties”)** are used to pass data from a **parent component to a child component** in React.

- Props are **read-only (immutable)**
- They help make components **reusable and dynamic**
- Data flows **one-way (parent → child)**

👉 Think of props like **function arguments**

---

## 📌 2. Syntax

### Passing Props (Parent → Child)

```jsx
function App() {
  return <User name="Prakash" age={25} />;
}
```

### Receiving Props (Child Component)

```jsx
function User(props) {
  return (
    <h1>
      {props.name} is {props.age} years old
    </h1>
  );
}
```

---

### ✅ Using Destructuring (Best Practice)

```jsx
function User({ name, age }) {
  return (
    <h1>
      {name} is {age}
    </h1>
  );
}
```

---

## 📌 3. Types of Props

### 1. String Props

```jsx
<Greeting message="Hello World" />
```

---

### 2. Number Props

```jsx
<User age={25} />
```

---

### 3. Boolean Props

```jsx
<Button isDisabled={true} />
```

---

### 4. Array Props

```jsx
<List items={["Apple", "Banana", "Mango"]} />
```

---

### 5. Object Props

```jsx
<User user={{ name: "Prakash", age: 25 }} />
```

---

### 6. Function Props (Very Important 🔥)

```jsx
function App() {
  const handleClick = () => alert("Clicked");

  return <Button onClick={handleClick} />;
}
```

---

## 📌 4. children Prop

**`children`** is a special prop used to pass content between component tags.

### Example:

```jsx
function Card({ children }) {
  return <div className="card">{children}</div>;
}
```

### Usage:

```jsx
<Card>
  <h1>Hello</h1>
  <p>This is inside card</p>
</Card>
```

👉 Output: Everything inside `<Card>` is passed as `children`

---

## 📌 5. Examples

### 🔹 Simple Example

```jsx
function Welcome({ name }) {
  return <h1>Welcome {name}</h1>;
}

function App() {
  return <Welcome name="Prakash" />;
}
```

---

### 🔹 Props with Function

```jsx
function Button({ handleClick }) {
  return <button onClick={handleClick}>Click Me</button>;
}
```

---

### 🔹 Props with List

```jsx
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

## 📌 6. Common Mistakes ❌

### ❌ 1. Modifying Props

```jsx
function User(props) {
  props.name = "Changed"; // ❌ Wrong
}
```

👉 Props are **immutable**

---

### ❌ 2. Forgetting Curly Braces

```jsx
<User age="25" />   // ❌ String instead of number
<User age={25} />   // ✅ Correct
```

---

### ❌ 3. Not Destructuring Properly

```jsx
function User(name) {
  // ❌ Wrong
}
```

---

### ❌ 4. Missing Key in Lists

```jsx
items.map((item) => <li>{item}</li>); // ❌
```

---

### ❌ 5. Overusing Props (Prop Drilling)

Passing props through many layers unnecessarily.

---

## 📌 7. Advanced (Hard Example) 🔥

### 🎯 Scenario: Product Dashboard

```jsx
function App() {
  const products = [
    { id: 1, name: "Laptop", price: 50000 },
    { id: 2, name: "Phone", price: 20000 },
  ];

  const handleBuy = (product) => {
    alert(`Bought ${product.name}`);
  };

  return (
    <div>
      <h1>Products</h1>
      <ProductList products={products} onBuy={handleBuy} />
    </div>
  );
}
```

---

### Child Component (List)

```jsx
function ProductList({ products, onBuy }) {
  return (
    <div>
      {products.map((product) => (
        <ProductCard key={product.id} product={product} onBuy={onBuy} />
      ))}
    </div>
  );
}
```

---

### Child Component (Card)

```jsx
function ProductCard({ product, onBuy }) {
  return (
    <div style={{ border: "1px solid black", margin: "10px" }}>
      <h2>{product.name}</h2>
      <p>₹{product.price}</p>
      <button onClick={() => onBuy(product)}>Buy</button>
    </div>
  );
}
```

---

### 🔥 Concepts Covered:

- Passing **objects as props**
- Passing **functions as props**
- **Component composition**
- **Reusable UI**
- **Event handling via props**

---

## 📌 8. My Understanding (Simple Words)

Props are like **data carriers** in React.

- Parent sends data → Child receives data
- Props make components **dynamic & reusable**
- Props cannot be changed inside child
- You can pass anything:
  👉 string, number, array, object, function, JSX

👉 In short:

> **Props = Inputs of a React Component**

---

## ✅ Practice Questions

1. Create a `UserCard` component that shows name, age, and city.
2. Pass a function as prop and trigger it on button click.
3. Create a `Wrapper` component using `children`.
4. Build a reusable `Button` component with dynamic label.
5. Create a `BlogList` component using array props.

---

---

# 📘 Wrapper Component using `children`

## 📌 Problem

Create a reusable **Wrapper component** that can wrap any content using `children`.

---

## ✅ Solution (Step by Step)

### 🔹 1. Wrapper Component

```jsx id="wrapper01"
function Wrapper({ children }) {
  return (
    <div
      style={{
        border: "2px solid black",
        padding: "20px",
        borderRadius: "10px",
        backgroundColor: "#f5f5f5",
        margin: "10px",
      }}
    >
      {children}
    </div>
  );
}
```

---

### 🔹 2. Using Wrapper Component

```jsx id="wrapper02"
function App() {
  return (
    <div>
      <Wrapper>
        <h1>Hello Prakash</h1>
        <p>This is inside wrapper</p>
      </Wrapper>

      <Wrapper>
        <button>Click Me</button>
      </Wrapper>
    </div>
  );
}
```

---

## 🎯 Output Concept

- First Wrapper → wraps heading + paragraph
- Second Wrapper → wraps button

👉 Same component reused for different UI

---

## 🔥 Hard Example (Real-world usage)

### 🎯 Card Layout System

```jsx id="wrapper03"
function Card({ children }) {
  return (
    <div
      style={{
        width: "250px",
        border: "1px solid #ccc",
        padding: "15px",
        borderRadius: "8px",
        boxShadow: "0 2px 5px rgba(0,0,0,0.2)",
        margin: "10px",
      }}
    >
      {children}
    </div>
  );
}
```

---

### Usage:

```jsx id="wrapper04"
function App() {
  return (
    <div style={{ display: "flex" }}>
      <Card>
        <h2>Laptop</h2>
        <p>Price: ₹50000</p>
        <button>Buy</button>
      </Card>

      <Card>
        <h2>Phone</h2>
        <p>Price: ₹20000</p>
        <button>Buy</button>
      </Card>
    </div>
  );
}
```

---

## 🧠 Key Understanding

- `children` allows you to pass **JSX inside a component**
- It makes components **flexible & reusable**
- You don’t need to define specific props for every content

---

## ❌ Common Mistake

```jsx id="wrapper05"
function Wrapper() {
  return <div>{props.children}</div>; // ❌ props not defined
}
```

✅ Correct:

```jsx id="wrapper06"
function Wrapper(props) {
  return <div>{props.children}</div>;
}
```

---

## 🔥 Bonus (Advanced Pattern)

### Multiple Slots Pattern

```jsx id="wrapper07"
function Layout({ header, children, footer }) {
  return (
    <div>
      <header>{header}</header>
      <main>{children}</main>
      <footer>{footer}</footer>
    </div>
  );
}
```

### Usage:

```jsx id="wrapper08"
<Layout header={<h1>My App</h1>} footer={<p>© 2026</p>}>
  <p>Main Content</p>
</Layout>
```

---

## 🚀 Final Thought

> `children` = “Whatever you put inside the component”

---

If you want next step 🔥
I can give you:

- Real-world UI patterns using `children`
- Compound components pattern (used in big apps)
- Props + children interview questions
