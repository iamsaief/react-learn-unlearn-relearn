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
  - [💡 Simple Analogy: Cooking with a Timer](#-simple-analogy-cooking-with-a-timer)
  - [📝 Example 1: Fetching API Data When the Component Mounts](#-example-1-fetching-api-data-when-the-component-mounts)
  - [📝 Example 2: Cleaning Up Event Listeners](#-example-2-cleaning-up-event-listeners)
  - [📌 Common Mistake](#-common-mistake)
  - [📌 Where You’ll See This in the Real World](#-where-youll-see-this-in-the-real-world)
- [2. 📜 `useState()` Explained – Managing Component State Like a Pro](#2--usestate-explained--managing-component-state-like-a-pro)
  - [💡 Simple Analogy: Using a Notepad for Quick Notes](#-simple-analogy-using-a-notepad-for-quick-notes)
  - [📝 Example 1: Creating a Simple Counter](#-example-1-creating-a-simple-counter)
  - [📝 Example 2: Handling Asynchronous State Updates](#-example-2-handling-asynchronous-state-updates)
  - [📌 Where You’ll See This in the Real World](#-where-youll-see-this-in-the-real-world-1)
- [3. 🔍 Harnessing `useRef()` – Direct DOM Access Without Re-Renders](#3--harnessing-useref--direct-dom-access-without-re-renders)
  - [💡 Simple Analogy: A Bookmark in a Book](#-simple-analogy-a-bookmark-in-a-book)
  - [📝 Example 1: Focusing an Input Field Programmatically](#-example-1-focusing-an-input-field-programmatically)
  - [📝 Example 2: Tracking Previous State Without Affecting Re-Renders](#-example-2-tracking-previous-state-without-affecting-re-renders)
  - [📌 Where You’ll See This in the Real World](#-where-youll-see-this-in-the-real-world-2)
- [4. 🌍 React Context API – Say Goodbye to Prop Drilling](#4--react-context-api--say-goodbye-to-prop-drilling)
  - [💡 Simple Analogy: A Public Bulletin Board](#-simple-analogy-a-public-bulletin-board)
  - [📝 Example 1: Creating a Theme Context](#-example-1-creating-a-theme-context)
  - [📝 Example 2: Using Context in Components](#-example-2-using-context-in-components)
  - [📌 Where You’ll See This in the Real World:](#-where-youll-see-this-in-the-real-world-3)
- [5. 🚀 Boosting React Performance with `React.memo()` \& `useMemo()`](#5--boosting-react-performance-with-reactmemo--usememo)
  - [💡 Simple Analogy: Using a Cheat Sheet Instead of Rewriting Notes](#-simple-analogy-using-a-cheat-sheet-instead-of-rewriting-notes)
  - [📝 Example 1: Preventing Unnecessary Re-Renders with `React.memo()`](#-example-1-preventing-unnecessary-re-renders-with-reactmemo)
  - [📝 Example 2: Optimizing Expensive Computations with `useMemo()`](#-example-2-optimizing-expensive-computations-with-usememo)
  - [📌 Where You’ll See This in the Real World:](#-where-youll-see-this-in-the-real-world-4)
- [6. ⚙️ Optimizing Performance with `useCallback()` – Prevent Unnecessary Function Re-Creation](#6-️-optimizing-performance-with-usecallback--prevent-unnecessary-function-re-creation)
  - [💡 Simple Analogy: Giving Instructions Instead of Repeating a Recipe](#-simple-analogy-giving-instructions-instead-of-repeating-a-recipe)
  - [📝 Example 1 (Simple): Memoizing a Click Handler to Prevent Function Re-Creation](#-example-1-simple-memoizing-a-click-handler-to-prevent-function-re-creation)
  - [📝 Example 2 (Complex): Preventing Re-Renders in a Child Component](#-example-2-complex-preventing-re-renders-in-a-child-component)
  - [📌 Where You’ll See This in the Real World:](#-where-youll-see-this-in-the-real-world-5)
- [7. 🔁 `useReducer()` vs `useState()` – Managing Complex State Like a Pro](#7--usereducer-vs-usestate--managing-complex-state-like-a-pro)
  - [💡 Simple Analogy: A Mail Sorting System](#-simple-analogy-a-mail-sorting-system)
  - [📝 Example 1 (Simple): Basic Counter Using `useReducer()`](#-example-1-simple-basic-counter-using-usereducer)
  - [📝 Example 2 (Complex): Managing a Todo List](#-example-2-complex-managing-a-todo-list)
  - [📌 Where You’ll See This in the Real World:](#-where-youll-see-this-in-the-real-world-6)
- [8. 🔄 Creating Custom Hooks – Make Your React Code Reusable \& Scalable](#8--creating-custom-hooks--make-your-react-code-reusable--scalable)
  - [💡 Simple Analogy: Making a Universal Phone Charger Instead of Multiple Adapters](#-simple-analogy-making-a-universal-phone-charger-instead-of-multiple-adapters)
  - [📝 Example 1 (Simple): Creating a `useFetch()` Hook for API Calls](#-example-1-simple-creating-a-usefetch-hook-for-api-calls)
  - [📝 Example 2 (Complex): Creating a `useDebounce()` Hook to Improve Input Performance](#-example-2-complex-creating-a-usedebounce-hook-to-improve-input-performance)
  - [📌 Where You’ll See This in the Real World:](#-where-youll-see-this-in-the-real-world-7)
- [9. 📤 Mastering React Portals – Rendering Outside the Main DOM](#9--mastering-react-portals--rendering-outside-the-main-dom)
  - [💡 Simple Analogy: A VIP Entrance in a Theater](#-simple-analogy-a-vip-entrance-in-a-theater)
  - [📝 Example 1 (Simple): Creating a Modal Using Portals](#-example-1-simple-creating-a-modal-using-portals)
  - [📝 Example 2 (Complex): Creating a Click-to-Open Modal with Portals](#-example-2-complex-creating-a-click-to-open-modal-with-portals)
  - [📌 Where You’ll See This in the Real World:](#-where-youll-see-this-in-the-real-world-8)
- [10. ⚡ Unlocking Concurrent Rendering – Making React Apps Faster \& Smoother](#10--unlocking-concurrent-rendering--making-react-apps-faster--smoother)
  - [💡 Simple Analogy: Ordering Coffee While Waiting for Food](#-simple-analogy-ordering-coffee-while-waiting-for-food)
  - [📝 Example 1 (Simple): Using `startTransition()` to Prioritize UI Updates](#-example-1-simple-using-starttransition-to-prioritize-ui-updates)
  - [📝 Example 2 (Complex): Preventing UI Freezes in Large Lists](#-example-2-complex-preventing-ui-freezes-in-large-lists)
  - [📌 Where You’ll See This in the Real World](#-where-youll-see-this-in-the-real-world-9)

---

Available In: [🇧🇩 বাংলা](./bn-BD/README_bn-BD.md)

---

## 1. ⚡ Mastering `useEffect()` – React’s Side Effect Powerhouse

**🔹 Introduction**

React’s `useEffect()` hook lets you **handle side effects** in functional components—things like **data fetching, event listeners, subscriptions, or updating the DOM** outside React’s render cycle. Without `useEffect()`, you’d have to **manually manage side effects inside lifecycle methods** like `componentDidMount()` or `componentDidUpdate()`.

### 💡 Simple Analogy: Cooking with a Timer

Imagine you’re boiling water while preparing a meal. You set up a **timer to ensure the water boils at the right time**. Similarly, useEffect() runs certain actions **after the component renders**, ensuring they execute **only when necessary**.

### 📝 Example 1: Fetching API Data When the Component Mounts

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

### 📝 Example 2: Cleaning Up Event Listeners

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

### 💡 Simple Analogy: Using a Notepad for Quick Notes

Think of `useState()` like a **sticky note**—you jot down information, **update it anytime**, and **refer to it when needed**. Unlike normal variables, React **remembers** `useState()` **values between renders**.

### 📝 Example 1: Creating a Simple Counter

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

### 📝 Example 2: Handling Asynchronous State Updates

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

### 💡 Simple Analogy: A Bookmark in a Book

Imagine placing a **bookmark in a book** to quickly find a page. The bookmark **stays in place** regardless of how many times you read the book. Similarly, useRef() stores a value **without causing the component to re-render**, unlike state updates.

### 📝 Example 1: Focusing an Input Field Programmatically

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

### 📝 Example 2: Tracking Previous State Without Affecting Re-Renders

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

### 💡 Simple Analogy: A Public Bulletin Board

Instead of individually delivering messages **to every person** in a building, a **bulletin board** allows anyone to read shared information. Similarly, React Context API **shares data globally**, avoiding deep prop chains.

### 📝 Example 1: Creating a Theme Context

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

### 📝 Example 2: Using Context in Components

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

### 💡 Simple Analogy: Using a Cheat Sheet Instead of Rewriting Notes

Memoization **stores previously computed values** to **avoid redundant recalculations**. It’s like **writing answers on a cheat sheet** instead of **solving the same problems over and over**.

### 📝 Example 1: Preventing Unnecessary Re-Renders with `React.memo()`

```jsx
import React from "react";

const MemoizedComponent = React.memo(({ count }) => <div>Count: {count}</div>);
```

**💡 Explanation:**

- `React.memo()` ensures **this component only re-renders if count changes**, reducing unnecessary updates.

**📌 Common Mistake:** Using `React.memo()` for **components with changing child elements**, leading to **unexpected render behavior**.

### 📝 Example 2: Optimizing Expensive Computations with `useMemo()`

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

## 6. ⚙️ Optimizing Performance with `useCallback()` – Prevent Unnecessary Function Re-Creation

**🛠️ Introduction**

Every time a **React component re-renders**, any **function declared inside it is re-created**. In most cases, this is fine, but when functions are passed to **child components**, unnecessary re-creations can cause **performance issues**.

`useCallback()` memoizes functions, ensuring they are only re-created when necessary.

### 💡 Simple Analogy: Giving Instructions Instead of Repeating a Recipe

Imagine you’re **teaching someone how to cook pasta**. Instead of **repeating the recipe every time**, you write the instructions **once**, and they refer to the written notes whenever needed.

Similarly, `useCallback()` **stores functions in memory**, preventing React from **re-creating them unnecessarily**.

### 📝 Example 1 (Simple): Memoizing a Click Handler to Prevent Function Re-Creation

```jsx
import { useState, useCallback } from "react";

const Counter = () => {
  const [count, setCount] = useState(0);

  const increment = useCallback(() => {
    setCount((prevCount) => prevCount + 1);
  }, []);

  return <button onClick={increment}>Count: {count}</button>;
};
```

**💡 Explanation:**

- `useCallback(() => setCount(prevCount + 1), [])` **ensures the function is created only once**, instead of on every re-render.
- Without `useCallback()`, **React would re-create `increment()` every time**, making the app **less efficient**.

### 📝 Example 2 (Complex): Preventing Re-Renders in a Child Component

```jsx
import { useState, useCallback, memo } from "react";

const Child = memo(({ handleClick }) => {
  console.log("Child component re-rendered!");
  return <button onClick={handleClick}>Click Me</button>;
});

const Parent = () => {
  const [count, setCount] = useState(0);

  const handleClick = useCallback(() => {
    setCount((prevCount) => prevCount + 1);
  }, []);

  return (
    <div>
      <p>Count: {count}</p>
      <Child handleClick={handleClick} />
    </div>
  );
};
```

**💡 Explanation:**

- The `Child` component is wrapped with` memo()`, meaning it **only re-renders when its props change**.
- **Without `useCallback()`, `handleClick()` would be re-created every render**, causing `Child` to **re-render unnecessarily**.

**📌 Common Mistake:** Using `useCallback()` **for functions that don’t need memoization**, unnecessarily **complicating code**.

### 📌 Where You’ll See This in the Real World:

- **Optimizing list rendering when passing callbacks to child components**
- **Avoiding unnecessary function re-renders in heavy UI interactions**
- **Reducing expensive calculations inside event handlers**

<br>

## 7. 🔁 `useReducer()` vs `useState()` – Managing Complex State Like a Pro

**🧩 Introduction**

While `useState()` is great for **simple state updates**, managing **complex state transitions** can quickly become **messy and inefficient**—especially when handling multiple state values that depend on each other.

React’s `useReducer()` **provides a structured approach** by using a **pure function (reducer) to process state updates** instead of manually modifying state within the component.

This pattern is similar to **Redux**, where instead of directly setting state, you **dispatch actions**, and the reducer decides **how the state should change**.

### 💡 Simple Analogy: A Mail Sorting System

Instead of manually **sorting each letter one by one** (`useState()`), a **mail sorting system (`useReducer()`) efficiently categorizes and processes mail**, making bulk handling **easier and more scalable**.

Similarly, `useReducer()` helps **structure complex state logic**, keeping updates **predictable and centralized**.

### 📝 Example 1 (Simple): Basic Counter Using `useReducer()`

```jsx
import { useReducer } from "react";

const reducer = (state, action) => {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };
    case "decrement":
      return { count: state.count - 1 };
    default:
      return state;
  }
};

const Counter = () => {
  const [state, dispatch] = useReducer(reducer, { count: 0 });

  return (
    <div>
      <p>Count: {state.count}</p>
      <button onClick={() => dispatch({ type: "increment" })}>Increase</button>
      <button onClick={() => dispatch({ type: "decrement" })}>Decrease</button>
    </div>
  );
};
```

**💡 Explanation:**

- **State is an object** (`{ count: 0 }`), allowing more structured updates.

- `dispatch({ type: "increment" })` **sends an action**, and the `reducer` function **determines how state should change** based on the action type.

- This approach **prevents unnecessary re-renders**, as **only specific state changes are triggered**.

**📌 Common Mistake:** Using `useReducer()` **for simple cases** where `useState()` is sufficient, making code needlessly complex.

### 📝 Example 2 (Complex): Managing a Todo List

```jsx
import { useReducer } from "react";

const reducer = (state, action) => {
  switch (action.type) {
    case "add":
      return [...state, { id: Date.now(), text: action.text }];
    case "remove":
      return state.filter((todo) => todo.id !== action.id);
    default:
      return state;
  }
};

const TodoApp = () => {
  const [todos, dispatch] = useReducer(reducer, []);

  return (
    <div>
      <button onClick={() => dispatch({ type: "add", text: "Learn React" })}>Add Todo</button>
      {todos.map((todo) => (
        <div key={todo.id}>
          <p>{todo.text}</p>
          <button onClick={() => dispatch({ type: "remove", id: todo.id })}>Remove</button>
        </div>
      ))}
    </div>
  );
};
```

**💡 Explanation:**

- Instead of managing multiple state variables separately (`useState()`), `useReducer()` organizes state in an **array** for **efficient updates**.

- **Adding a todo dispatches an `add` action**, where a new todo is created dynamically.

- **Removing a todo dispatches a `remove` action**, filtering out the selected todo without affecting others.

**📌 Common Mistake:** Modifying state directly (e.g., `state.push(todo)`) **instead of returning a new state array**, leading to **unexpected bugs**.

### 📌 Where You’ll See This in the Real World:

- **Managing global state transitions in large applications**
- **Handling complex user interactions that require multiple updates**
- **Using Redux-like patterns inside React without installing external libraries**

<br>

## 8. 🔄 Creating Custom Hooks – Make Your React Code Reusable & Scalable

**🛠️ Introduction**

React’s built-in hooks (`useState()`, `useEffect()`, etc.) **help simplify component logic**, but what if multiple components need the **same functionality**?

**Custom hooks** allow developers to **extract common logic** from components and **reuse them efficiently**, making code **cleaner, more scalable, and easier to maintain**.

Instead of **repeating logic across components**, a **custom hook centralizes it**, making updates **easier**.

### 💡 Simple Analogy: Making a Universal Phone Charger Instead of Multiple Adapters

Instead of **creating separate adapters** for each device, a **universal charger** simplifies **charging for all brands**.

Similarly, **custom hooks centralize logic**, allowing **multiple components to reuse it efficiently**.

### 📝 Example 1 (Simple): Creating a `useFetch()` Hook for API Calls

```jsx
import { useState, useEffect } from "react";

const useFetch = (url) => {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch(url)
      .then((res) => res.json())
      .then((json) => {
        setData(json);
        setLoading(false);
      });
  }, [url]);

  return { data, loading };
};

// Using the Custom Hook
const Component = () => {
  const { data, loading } = useFetch("https://api.example.com/data");
  return <div>{loading ? "Loading..." : JSON.stringify(data)}</div>;
};
```

**💡 Explanation:**

- **\*`useFetch(url)` handles API calls**, making it **reusable for multiple components**.

- This **prevents repetitive logic**, improving **maintainability**.

- Any component using `useFetch()` automati**cally gets loading state and data**, making it **simpler and more efficient**.

**📌 Common Mistake:** Not adding a **dependency array (`[url]`) in `useEffect()`**, leading to **uncontrolled API calls**.

### 📝 Example 2 (Complex): Creating a `useDebounce()` Hook to Improve Input Performance

```jsx
import { useState, useEffect } from "react";

const useDebounce = (value, delay) => {
  const [debouncedValue, setDebouncedValue] = useState(value);

  useEffect(() => {
    const handler = setTimeout(() => {
      setDebouncedValue(value);
    }, delay);

    return () => clearTimeout(handler);
  }, [value, delay]);

  return debouncedValue;
};

// Using the Custom Hook
const SearchBar = () => {
  const [query, setQuery] = useState("");
  const debouncedQuery = useDebounce(query, 500);

  useEffect(() => {
    console.log("Searching for:", debouncedQuery);
  }, [debouncedQuery]);

  return <input onChange={(e) => setQuery(e.target.value)} placeholder="Type to search..." />;
};
```

**💡 Explanation:**

- `useDebounce()` **delays state updates**, preventing **excessive API calls on every keystroke**.

- This **significantly improves performance** in **search bars, auto-suggestions, or real-time filtering**.

### 📌 Where You’ll See This in the Real World:

- **Fetching API data efficiently**
- **Handling authentication state globally**
- **Managing reusable UI behaviors** (animations, form validation, debounce functions, etc.)

<br>

## 9. 📤 Mastering React Portals – Rendering Outside the Main DOM

**🚪 Introduction**

React normally renders components **inside a parent tree**, but sometimes **you need to render elements outside that hierarchy**—for example:

- **Modals** that shouldn’t be affected by overflow styles
- **Tooltips** that need absolute positioning
- **Notifications** that appear globally

React **Portals allow components to be rendered outside their parent DOM, without breaking React’s state system**.

### 💡 Simple Analogy: A VIP Entrance in a Theater

Imagine **entering a theater through a special VIP entrance** instead of using **the main gate**.

Similarly, **React Portals allow components (like modals) to be rendered elsewhere** while still maintaining their React behavior.

### 📝 Example 1 (Simple): Creating a Modal Using Portals

```jsx
import ReactDOM from "react-dom";

const modalRoot = document.getElementById("modal-root");

const Modal = ({ children }) => {
  return ReactDOM.createPortal(children, modalRoot);
};
```

**💡 Explanation:**

- Instead of rendering inside the usual React tree, this **places the modal inside `modalRoot`**, avoiding **styling conflicts**.

- **Perfect for popups, overlays, and dynamically positioned UI elements**.

**📌 Common Mistake:** Using Portals **without a dedicated container (`modalRoot`)**, leading to **unexpected styling issues**.

### 📝 Example 2 (Complex): Creating a Click-to-Open Modal with Portals

```jsx
import { useState } from "react";
import ReactDOM from "react-dom";

const modalRoot = document.getElementById("modal-root");

const Modal = ({ children, onClose }) => {
  return ReactDOM.createPortal(
    <div style={{ background: "rgba(0,0,0,0.8)", padding: "20px" }}>
      <button onClick={onClose}>Close</button>
      {children}
    </div>,
    modalRoot
  );
};

const App = () => {
  const [open, setOpen] = useState(false);

  return (
    <div>
      <button onClick={() => setOpen(true)}>Open Modal</button>
      {open && <Modal onClose={() => setOpen(false)}>Hello from the Modal!</Modal>}
    </div>
  );
};
```

**💡 Explanation:**

- Clicking the **"Open Modal"** button renders the modal **inside `modalRoot`**, avoiding **overflow or z-index issues**.
- The **"Close" button dismisses the modal**, controlling its visibility **with React state**.

### 📌 Where You’ll See This in the Real World:

- **Creating modals without affecting the main UI structure**
- **Rendering tooltips that need proper positioning**
- **Managing notifications that should appear outside the main component hierarchy**

<br>

## 10. ⚡ Unlocking Concurrent Rendering – Making React Apps Faster & Smoother

**🚀 Introduction**

By default, React processes updates **synchronously**, meaning it **blocks other tasks** until rendering is complete. In complex applications, this can lead to **UI freezes, lag, and poor user experience**—especially when dealing with **large lists, animations, or expensive computations**.

React **Concurrent Rendering (React 18)** introduces techniques that **prioritize urgent UI tasks, deferring less important updates** to improve **responsiveness and efficiency**.

### 💡 Simple Analogy: Ordering Coffee While Waiting for Food

Imagine a **restaurant kitchen preparing food orders**. Instead of waiting for an **entire meal to cook**, the café **prioritizes quick coffee orders first** so customers **get their drinks instantly** while waiting for the food.

Similarly, **Concurrent Rendering ensures high-priority updates (like _user interactions_) are handled immediately**, while **lower-priority updates (like _data fetching_) are deferred**.

### 📝 Example 1 (Simple): Using `startTransition()` to Prioritize UI Updates

```jsx
import { useState, startTransition } from "react";

const SearchComponent = () => {
  const [query, setQuery] = useState("");
  const [results, setResults] = useState([]);

  const handleSearch = (input) => {
    setQuery(input); // Immediate UI update

    startTransition(() => {
      setResults(["Apple", "Banana", "Cherry"].filter((item) => item.toLowerCase().includes(input.toLowerCase())));
    });
  };

  return (
    <div>
      <input onChange={(e) => handleSearch(e.target.value)} placeholder="Search..." />
      <ul>
        {results.map((r, i) => (
          <li key={i}>{r}</li>
        ))}
      </ul>
    </div>
  );
};
```

**💡 Explanation:**

- `setQuery(input)` updates the search field **immediately** so users see their input without delay.
- **Using** `startTransition()`, React **defers list filtering**, preventing lag while the user types.
- **Improves performance** by ensuring fast UI updates even in **large datasets**.

**📌 Common Mistake:** Using `startTransition()` for **critical updates** (e.g., button clicks or form submissions)—this may **cause unexpected delays**.

### 📝 Example 2 (Complex): Preventing UI Freezes in Large Lists

```jsx
import { useState, useTransition } from "react";

const LargeList = ({ items }) => {
  const [isPending, startTransition] = useTransition();
  const [filteredItems, setFilteredItems] = useState([]);

  const handleFilter = (query) => {
    startTransition(() => {
      setFilteredItems(items.filter((item) => item.includes(query)));
    });
  };

  return (
    <div>
      <input onChange={(e) => handleFilter(e.target.value)} placeholder="Filter list..." />
      {isPending && <p>Updating list...</p>}
      <ul>
        {filteredItems.map((item, index) => (
          <li key={index}>{item}</li>
        ))}
      </ul>
    </div>
  );
};
```

**💡 Explanation:**

- `useTransition()` **allows React to prioritize user interactions** over expensive computations.
- Instead of **blocking the UI**, it **delays filtering operations** while showing a `"Updating list..."` message.
- Prevents **UI lag in lists with thousands of items**, improving **performance drastically**.

### 📌 Where You’ll See This in the Real World

- **Handling search inputs without freezing UI**
- **Preventing lag in large lists and data-heavy applications**
- **Improving user experience in animations and dynamic rendering**
