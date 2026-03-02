# React + Vite

# 🧠 Big Picture: What is React?

React is a **JavaScript library for building user interfaces**.

👉 Instead of manually changing the DOM, you describe what the UI should look like, and React updates it for you.

---

## 📁 public/index.html — The Entry HTML

```html
<div id="root"></div>
```

### What is this?

👉 This is the only HTML React uses.

React injects your entire app inside this `root` div.

---

## 📁 src/main.jsx — The Starting Point 🚀

This is where React begins execution.

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App.jsx";

ReactDOM.createRoot(document.getElementById("root")).render(<App />);
```

### What happens here?

1️⃣ Find the `root` div in HTML  
2️⃣ Create a React root  
3️⃣ Render the `<App />` component inside it

👉 This is the **entry point** of your React app.

---

## 📁 src/App.jsx — The Main Component

```jsx
function App() {
  return <h1>Hello, Saish 👋</h1>;
}

export default App;
```

👉 This is the main UI component.  
Everything you see on screen starts from here.

---

# 🧩 What is a Component?

A **component** is a reusable piece of UI.

### Example:

```jsx
function Navbar() {
  return <h2>My Website</h2>;
}
```

### Use it inside App:

```jsx
function App() {
  return (
    <div>
      <Navbar />
      <p>Welcome!</p>
    </div>
  );
}
```

👉 React builds UI like LEGO blocks 🧱

---

# 🔄 Flow of a React Program

Let’s trace what happens when you run:

```bash
npm run dev
```

---

## 🪜 Step-by-step Flow

### 1️⃣ Browser loads `index.html`

Contains:

```html
<div id="root"></div>
```

---

### 2️⃣ main.jsx runs

React finds the root div:

```js
document.getElementById("root");
```

---

### 3️⃣ React renders `<App />`

```jsx
render(<App />);
```

---

### 4️⃣ App component returns JSX

```jsx
<h1>Hello</h1>
```

---

### 5️⃣ JSX → converted to real DOM

React updates the page.

👉 You see content in the browser.

---

# 🔄 What happens when data changes?

React re-renders only the changed parts.

### Example:

```jsx
function App() {
  const name = "Saish";
  return <h1>Hello {name}</h1>;
}
```

If `name` changes → only text updates, not the whole page.

This is thanks to:

👉 **Virtual DOM**

---

# 🧠 Virtual DOM (Simple Explanation)

Instead of updating the real DOM directly:

1️⃣ React creates a virtual copy  
2️⃣ Compares changes  
3️⃣ Updates only what changed

👉 Faster performance ⚡

---

# 📦 How Components Work Together

### Example structure:

```
App
 ├── Navbar
 ├── Sidebar
 └── Content
      ├── Post
      └── Comments
```

### Flow:

1️⃣ App renders children  
2️⃣ Children render their children  
3️⃣ UI builds top → down

This is called:

👉 **Component Tree**

---

# 🔁 Data Flow in React

React uses **one-way data flow**.

👉 Parent → Child

### Example:

```jsx
function App() {
  return <Greeting name="Saish" />;
}

function Greeting(props) {
  return <h1>Hello {props.name}</h1>;
}
```

Data flows downward only.

---

# 🧠 React Flow Summary (One Screen)

```
index.html → main.jsx → App.jsx → Components → Browser UI
```

---

# 🧩 How a React App Runs (Real-world Analogy)

Think of React like a restaurant 🍽️

- index.html → table
- main.jsx → waiter
- App.jsx → head chef
- components → kitchen stations
- props → order details
- state → current cooking status
- DOM → food served to customer

---

# 🚀 What You Should Understand at This Stage

✔ Project structure  
✔ Components = building blocks  
✔ JSX = UI syntax  
✔ main.jsx = entry point  
✔ App.jsx = root component  
✔ Data flows top → down
