<div align="center">
  <img height="80" src="https://svgmix.com/uploads/e86a0a-react.svg">
  <h1>React: Learn, Unlearn & Relearn ⚛️</h1>
</div>

Test your React knowledge, refresh important concepts, or prepare for an interview with this **comprehensive guide!** 💪 Whether you're a beginner or an intermediate learner, this document will help you strengthen your understanding with **detailed explanations, multiple examples, common pitfalls, and real-world applications.**

I created this for **fun and learning in my free time**, so please forgive any mistakes! If you find it helpful, I’d truly appreciate a ⭐️ or a reference to this repo.

Best of luck on your programming journey—🙏✨ **Happy coding!** ⚛️💻

<p align="center">
💬 In case you want to reach out or just say hi, ↩️ <br/>
<a href="https://www.facebook.com/saiefalemon">Facebook</a> | <a href="https://www.linkedin.com/in/saiefalemon">LinkedIn</a> | <a href="https://www.iamsaief.com/">Blog</a>
</p>

---

- [1. ⚡ Mastering `useEffect()` – React’s Side Effect Powerhouse](#1--mastering-useeffect--reacts-side-effect-powerhouse)
  - [🔹 💡 Simple Analogy: Cooking with a Timer](#--simple-analogy-cooking-with-a-timer)
  - [🔹 Example 1: Fetching API Data When the Component Mounts](#-example-1-fetching-api-data-when-the-component-mounts)
  - [🔹 Example 2: Cleaning Up Event Listeners](#-example-2-cleaning-up-event-listeners)
  - [📌 Common Mistake](#-common-mistake)
  - [📌 Where You’ll See This in the Real World](#-where-youll-see-this-in-the-real-world)
- [2. 📜 `useState()` Explained – Managing Component State Like a Pro](#2--usestate-explained--managing-component-state-like-a-pro)
  - [🔹 💡 Simple Analogy: Using a Notepad for Quick Notes](#--simple-analogy-using-a-notepad-for-quick-notes)
  - [🔹 Example 1: Creating a Simple Counter](#-example-1-creating-a-simple-counter)
  - [🔹 Example 2: Handling Asynchronous State Updates](#-example-2-handling-asynchronous-state-updates)
  - [📌 Where You’ll See This in the Real World](#-where-youll-see-this-in-the-real-world-1)
- [3. 🔍 Harnessing `useRef()` – Direct DOM Access Without Re-Renders](#3--harnessing-useref--direct-dom-access-without-re-renders)
  - [🔹 💡 Simple Analogy: A Bookmark in a Book](#--simple-analogy-a-bookmark-in-a-book)
  - [🔹 Example 1: Focusing an Input Field Programmatically](#-example-1-focusing-an-input-field-programmatically)
  - [🔹 Example 2: Tracking Previous State Without Affecting Re-Renders](#-example-2-tracking-previous-state-without-affecting-re-renders)
  - [📌 Where You’ll See This in the Real World](#-where-youll-see-this-in-the-real-world-2)
- [4. 🌍 React Context API – Say Goodbye to Prop Drilling](#4--react-context-api--say-goodbye-to-prop-drilling)
  - [🔹 💡 Simple Analogy: A Public Bulletin Board](#--simple-analogy-a-public-bulletin-board)
  - [🔹 Example 1: Creating a Theme Context](#-example-1-creating-a-theme-context)
  - [🔹 Example 2: Using Context in Components](#-example-2-using-context-in-components)
  - [📌 Where You’ll See This in the Real World:](#-where-youll-see-this-in-the-real-world-3)
- [5. 🚀 Boosting React Performance with `React.memo()` \& `useMemo()`](#5--boosting-react-performance-with-reactmemo--usememo)
  - [🔹 💡 Simple Analogy: Using a Cheat Sheet Instead of Rewriting Notes](#--simple-analogy-using-a-cheat-sheet-instead-of-rewriting-notes)
  - [🔹 Example 1: Preventing Unnecessary Re-Renders with `React.memo()`](#-example-1-preventing-unnecessary-re-renders-with-reactmemo)
  - [🔹 Example 2: Optimizing Expensive Computations with `useMemo()`](#-example-2-optimizing-expensive-computations-with-usememo)
  - [📌 Where You’ll See This in the Real World:](#-where-youll-see-this-in-the-real-world-4)

---

Available In: [🇧🇩 বাংলা](./bn-BD/README_bn-BD.md)

---

## 1. ⚡ Mastering `useEffect()` – React’s Side Effect Powerhouse

**🔹 Introduction**
React’s `useEffect()` hook lets you **handle side effects** in functional components—things like **data fetching, event listeners, subscriptions, or updating the DOM** outside React’s render cycle. Without `useEffect()`, you’d have to **manually manage side effects inside lifecycle methods** like `componentDidMount()` or `componentDidUpdate()`.

### 🔹 💡 Simple Analogy: Cooking with a Timer

Imagine you’re boiling water while preparing a meal. You set up a **timer to ensure the water boils at the right time**. Similarly, useEffect() runs certain actions **after the component renders**, ensuring they execute **only when necessary**.

### 🔹 Example 1: Fetching API Data When the Component Mounts

```jsx
import { useEffect, useState } from "react";

const FetchComponent = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch("https://api.example.com/data")
      .then((response) => response.json())
      .then((json) => setData(json));
  }, []);

  return <div>{data ? JSON.stringify(data) : "Loading..."}</div>;
};
```

**💡 Explanation:**

- The **empty dependency array (`[]`)** ensures this effect runs **only once**, just like `componentDidMount()`.
- Without `useEffect()`, the API call would **run on every render**, causing **performance issues**.

### 🔹 Example 2: Cleaning Up Event Listeners

```jsx
import { useEffect } from "react";

const ResizeComponent = () => {
  useEffect(() => {
    const handleResize = () => console.log("Window resized!");

    window.addEventListener("resize", handleResize);
    return () => window.removeEventListener("resize", handleResize); // Cleanup
  }, []);

  return <div>Resize your window to see the effect.</div>;
};
```

**💡 Explanation:**

- The cleanup function **removes the event listener** when the component unmounts, preventing **memory leaks**.

### 📌 Common Mistake

Forgetting to **remove event listeners**, leading to unnecessary listeners stacking up.

### 📌 Where You’ll See This in the Real World

- **Fetching API data** when a component loads
- **Setting up intervals for animations**
- **Managing WebSocket connections**

<br>

## 2. 📜 `useState()` Explained – Managing Component State Like a Pro

**🔹 Introduction**
State allows React components to **track dynamic data** and **re-render when the data changes**. `useState()` is the most **fundamental React Hook**, replacing `this.state` in class components.

### 🔹 💡 Simple Analogy: Using a Notepad for Quick Notes

Think of `useState()` like a **sticky note**—you jot down information, **update it anytime**, and **refer to it when needed**. Unlike normal variables, React **remembers** `useState()` **values between renders**.

### 🔹 Example 1: Creating a Simple Counter

```jsx
import { useState } from "react";

const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
};
```

**💡 Explanation:**

- `useState(0)` initializes state with `0`.
- `setCount(count + 1)` updates state and **triggers a re-render**.

**📌 Common Mistake:** Modifying state **directly** (`count = 5`), which **won’t trigger a re-render**.

### 🔹 Example 2: Handling Asynchronous State Updates

```jsx
import { useState, useEffect } from "react";

const MessageComponent = () => {
  const [message, setMessage] = useState("");

  useEffect(() => {
    setTimeout(() => setMessage("Data Loaded!"), 2000);
  }, []);

  return <p>{message || "Loading..."}</p>;
};
```

**💡 Explanation:**

- The **state updates asynchronously** after **2 seconds**, simulating real-world API responses.

### 📌 Where You’ll See This in the Real World

- **Managing user input** (search bars, forms)
- **Handling UI state** (modals, notifications)
- **Storing API responses**

<br>

## 3. 🔍 Harnessing `useRef()` – Direct DOM Access Without Re-Renders

**🔹 Introduction**
React’s `useRef()` **stores values that persist across renders** without triggering a component re-render. Unlike useState(), updating a ref **doesn’t cause the UI to re-render**, making it ideal for:

- **Accessing and controlling DOM elements directly** (like input focus)
- **Tracking previous values without affecting performance**
- **Optimizing expensive calculations in complex UI interactions**

Without `useRef()`, you’d have to **store values in state**, which could cause **unnecessary re-renders**.

### 🔹 💡 Simple Analogy: A Bookmark in a Book

Imagine placing a **bookmark in a book** to quickly find a page. The bookmark **stays in place** regardless of how many times you read the book. Similarly, useRef() stores a value **without causing the component to re-render**, unlike state updates.

### 🔹 Example 1: Focusing an Input Field Programmatically

```jsx
import { useRef } from "react";

const InputFocus = () => {
  const inputRef = useRef(null);

  return (
    <div>
      <input ref={inputRef} />
      <button onClick={() => inputRef.current.focus()}>Focus Input</button>
    </div>
  );
};
```

**💡 Explanation:**

- `useRef(null)` initializes a **reference to an input element**.
- Clicking the button **calls `inputRef.current.focus()`**, directly interacting with the DOM.
- Unlike `useState()`, **changing a ref doesn’t trigger a re-render**, ensuring better performance.

**📌 Common Mistake:** Expecting `useRef()` **to trigger re-renders** when its value updates—**it doesn’t**.

### 🔹 Example 2: Tracking Previous State Without Affecting Re-Renders

```jsx
import { useRef, useEffect, useState } from "react";

const PrevValue = () => {
  const [count, setCount] = useState(0);
  const prevCountRef = useRef(count);

  useEffect(() => {
    prevCountRef.current = count;
  }, [count]);

  return (
    <div>
      <p>Current Count: {count}</p>
      <p>Previous Count: {prevCountRef.current}</p>
      <button onClick={() => setCount(count + 1)}>Increase</button>
    </div>
  );
};
```

**💡 Explanation:**

- `prevCountRef.current` **stores the previous value** of `count` without causing extra renders.
- On every `count` update, **the effect updates** `prevCountRef.current`, preserving the last value.
- Unlike `useState()`, changing `useRef()` values **doesn’t trigger re-renders**.

### 📌 Where You’ll See This in the Real World

- **Handling uncontrolled form inputs efficiently**
- **Tracking previous values for animations or calculations**
- **Storing mutable values that shouldn’t cause re-renders**

<br>

## 4. 🌍 React Context API – Say Goodbye to Prop Drilling

**🔹 Introduction**
React Context API solves the **problem of prop drilling**, where data needs to be passed **multiple levels deep** through props. Instead of manually passing data through multiple components, Context API **provides a global state that any component can access**.

### 🔹 💡 Simple Analogy: A Public Bulletin Board

Instead of individually delivering messages **to every person** in a building, a **bulletin board** allows anyone to read shared information. Similarly, React Context API **shares data globally**, avoiding deep prop chains.

### 🔹 Example 1: Creating a Theme Context

```jsx
import { createContext } from "react";

const ThemeContext = createContext("light");

const App = () => (
  <ThemeContext.Provider value="dark">
    <ChildComponent />
  </ThemeContext.Provider>
);
```

**💡 Explanation:**

- `createContext()` initializes a global theme.
- `Provider` **wraps child components**, allowing them to access the theme value (`dark`).

**📌 Common Mistake:** Forgetting to **wrap components in a Provider**, leading to `undefined` context values.

### 🔹 Example 2: Using Context in Components

```jsx
import { useContext } from "react";

const theme = useContext(ThemeContext);
return <div style={{ backgroundColor: theme === "dark" ? "#333" : "#fff" }}>Theme: {theme}</div>;
```

**💡 Explanation:**

- `useContext(ThemeContext)` **fetches the nearest provided value**, avoiding **manual prop passing**.

### 📌 Where You’ll See This in the Real World:

- **Authentication state management**
- **Theme switching & user preferences**
- **Multi-language support across components**

<br>

## 5. 🚀 Boosting React Performance with `React.memo()` & `useMemo()`

**🔹 Introduction**
React **re-renders components** when their state or props change, but sometimes **re-renders are unnecessary**. `React.memo()` and `useMemo()` **optimize performance** by **skipping unnecessary recalculations**.

### 🔹 💡 Simple Analogy: Using a Cheat Sheet Instead of Rewriting Notes

Memoization **stores previously computed values** to **avoid redundant recalculations**. It’s like **writing answers on a cheat sheet** instead of **solving the same problems over and over**.

### 🔹 Example 1: Preventing Unnecessary Re-Renders with `React.memo()`

```jsx
import React from "react";

const MemoizedComponent = React.memo(({ count }) => <div>Count: {count}</div>);
```

**💡 Explanation:**

- `React.memo()` ensures **this component only re-renders if count changes**, reducing unnecessary updates.

**📌 Common Mistake:** Using `React.memo()` for **components with changing child elements**, leading to **unexpected render behavior**.

### 🔹 Example 2: Optimizing Expensive Computations with `useMemo()`

```jsx
import { useMemo, useState } from "react";

const ExpensiveCalculation = ({ num }) => {
  const squaredNumber = useMemo(() => num * num, [num]);

  return <p>Squared: {squaredNumber}</p>;
};
```

**💡 Explanation:**

- `useMemo()` **caches** the computed value to **avoid recalculating on every render**.

### 📌 Where You’ll See This in the Real World:

- **Optimizing large lists or complex calculations**
- **Preventing unnecessary component re-renders**
- **Reducing lag in UI-heavy applications**

<br>
