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

**🗂️ Table of Content**

- [1. ⚡ Mastering `useEffect()` – React’s Side Effect Powerhouse](#1--mastering-useeffect--reacts-side-effect-powerhouse)
- [2. 📜 `useState()` Explained – Managing Component State Like a Pro](#2--usestate-explained--managing-component-state-like-a-pro)
- [3. 🔍 Harnessing `useRef()` – Direct DOM Access Without Re-Renders](#3--harnessing-useref--direct-dom-access-without-re-renders)
- [4. 🌍 React Context API – Say Goodbye to Prop Drilling](#4--react-context-api--say-goodbye-to-prop-drilling)
- [5. 🚀 Boosting React Performance with `React.memo()` \& `useMemo()`](#5--boosting-react-performance-with-reactmemo--usememo)
- [6. ⚙️ Optimizing Performance with `useCallback()` – Prevent Unnecessary Function Re-Creation](#6-️-optimizing-performance-with-usecallback--prevent-unnecessary-function-re-creation)
- [7. 🔁 `useReducer()` vs `useState()` – Managing Complex State Like a Pro](#7--usereducer-vs-usestate--managing-complex-state-like-a-pro)
- [8. 🔄 Creating Custom Hooks – Make Your React Code Reusable \& Scalable](#8--creating-custom-hooks--make-your-react-code-reusable--scalable)
- [9. 📤 Mastering React Portals – Rendering Outside the Main DOM](#9--mastering-react-portals--rendering-outside-the-main-dom)
- [10. ⚡ Unlocking Concurrent Rendering – Making React Apps Faster \& Smoother](#10--unlocking-concurrent-rendering--making-react-apps-faster--smoother)

---

Available In: [🇧🇩 বাংলা](./bn-BD/README_bn-BD.md)

---

## 1. ⚡ Mastering `useEffect()` – React’s Side Effect Powerhouse

**🛠️ Introduction**

React’s useEffect() hook lets you manage **side effects** in functional components—like fetching data, updating the DOM, or subscribing to events. It replaces lifecycle methods such as `componentDidMount()` and `componentDidUpdate()` with a cleaner, more unified API.

### 💡 Simple Analogy: Cooking with a Timer

Think of React rendering your component like prepping a meal. Some tasks—like boiling water—need to happen after prep, not during. `useEffect()` acts like a timer, ensuring those tasks run **after rendering**, and even lets you **clean up afterward**, like turning off the stove.

### 📝 Example 1 (Simple): Fetching API Data on Mount

```jsx
import { useEffect, useState } from "react";

const FetchData = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch("https://api.example.com/data")
      .then((res) => res.json())
      .then(setData);
  }, []);

  return <div>{data ? JSON.stringify(data) : "Loading..."}</div>;
};
```

**💬 Step-by-Step Explanation:**

- `useEffect()` runs after render.
- Empty dependency array `[]` makes it run **once**—like `componentDidMount()`.
- Fetch is executed, state is set, component re-renders with updated data.

### 📝 Example 2 (Complex): Adding & Cleaning Up an Event Listener

```jsx
import { useEffect } from "react";

const ResizeLogger = () => {
  useEffect(() => {
    const logResize = () => console.log("Window resized");
    window.addEventListener("resize", logResize);

    return () => {
      window.removeEventListener("resize", logResize);
    };
  }, []);

  return <p>Resize the window to log activity.</p>;
};
```

**💬 Step-by-Step Explanation:**

- Mount phase: event listener added.
- Unmount phase: cleanup function removes listener.
- Prevents memory leaks and redundant bindings.

### ❌ Common Pitfalls

| 🚩 Issue                    | 😵 What Goes Wrong                                                         |
| --------------------------- | -------------------------------------------------------------------------- |
| 🔁 Missing dependency array | Causes the effect to run on **every re-render**, leading to infinite loops |
| 🧼 Skipping cleanup logic   | Leads to **memory leaks**, lingering listeners or timers                   |
| ⚡ Overusing `useEffect()`  | Putting too much logic inside effects makes code **hard to maintain**      |
| 🔄 Incorrect dependencies   | Causes inconsistent behavior or stale data rendering                       |

### 🧾 TL;DR – Quick Reference

| 📍 Use Case              | ✅ Strategy                            |
| ------------------------ | -------------------------------------- |
| Run once on mount        | `useEffect(() => {...}, [])`           |
| Run on state change      | `useEffect(() => {...}, [stateVar])`   |
| Cleanup on unmount       | Return a function inside `useEffect()` |
| Watch multiple variables | `useEffect(() => {...}, [a, b, c])`    |

### 📌 Real-World Use Cases

- Fetching API data on component load
- Subscribing/unsubscribing from WebSocket or Firebase
- DOM manipulation like scroll or resize
- Tracking page visits and analytics
- Managing intervals or timeouts

<br>

## 2. 📜 `useState()` Explained – Managing Component State Like a Pro

**🛠️ Introduction**

State is what makes your React components dynamic. Before hooks, you had to use `this.state` inside class components. Now, with `useState()`, you can **track and update values** inside **functional components** effortlessly. It’s the **cornerstone hook** for managing local component data.

### 💡 Simple Analogy: Using a Sticky Note

Imagine you're working at a desk and jotting quick notes on sticky pads—each one stores a value you can **edit, replace, or remove easily**. `useState()` does the same for your component: store something (like a count), update it, and React will re-render the UI accordingly.

### 📝 Example 1 (Simple): Creating a Counter

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

**💬 Explanation:**

- `useState(0)` creates a state value called `count` and a function `setCount` to update it.
- React re-renders the component **every time `setCount()` updates the value**.

### 📝 Example 2 (Complex): Managing Form Input

```jsx
import { useState } from "react";

const ContactForm = () => {
  const [form, setForm] = useState({ name: "", email: "" });

  const handleChange = (e) => {
    setForm({ ...form, [e.target.name]: e.target.value });
  };

  return (
    <form>
      <input name="name" onChange={handleChange} value={form.name} />
      <input name="email" onChange={handleChange} value={form.email} />
      <p>
        Hello {form.name}, we’ll contact you at {form.email}.
      </p>
    </form>
  );
};
```

**💬 Explanation:**

- You can use `useState()` to manage **objects**, not just primitive values.
- The `handleChange` function updates `form` values without mutating the entire state manually.

### 📝 Example 3: Handling Asynchronous State Updates

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

**💬 Explanation:**

- The **state updates asynchronously** after **2 seconds**, simulating real-world API responses.

### ❌ Common Pitfalls

| 🚩 Issue                    | 😵 What Goes Wrong                                                          |
| --------------------------- | --------------------------------------------------------------------------- |
| 🛑 Directly modifying state | Doing `count = count + 1` won’t trigger a re-render—always use `setState()` |
| 🔁 Asynchronous updates     | Multiple `setState` calls in a row may not immediately reflect changes      |
| 💡 Forgetting immutability  | Overwriting nested state can lead to data loss if not handled properly      |

### 🧾 TL;DR – Quick Reference

| 🧩 Pattern           | 💬 What It Does                                       |
| -------------------- | ----------------------------------------------------- |
| `useState(default)`  | Creates a reactive state variable                     |
| `setState(newValue)` | Triggers a re-render with the new value               |
| Managing objects     | Use `{ ...prev, key: value }` to update partial state |
| Managing arrays      | Use `[...prev, newItem]` to add or update items       |

### 📌 Real-World Use Cases

- Tracking user interactions (clicks, toggles, tabs)
- Managing form inputs and validations
- Handling modal open/close states
- Storing local preferences like theme or filters

<br>

## 3. 🔍 Harnessing `useRef()` – Direct DOM Access Without Re-Renders

**🛠️ Introduction**

`useRef()` is a versatile hook that lets you **store mutable values** that persist across renders without causing a re-render. It’s most commonly used to:

- **Access DOM elements directly**
- **Track values without triggering updates**
- **Hold references to timers, previous state, or external libraries**

### 💡 Simple Analogy: A Bookmark in a Book

Imagine marking a page with a bookmark—it stays in place no matter how many times you open and close the book. Likewise, `useRef()` gives you **persistent access to a value** without altering the visible content (re-render).

### 📝 Example 1 (Simple): Focusing an Input Field

```jsx
import { useRef } from "react";

const AutoFocusInput = () => {
  const inputRef = useRef(null);

  return (
    <div>
      <input ref={inputRef} />
      <button onClick={() => inputRef.current.focus()}>Focus Input</button>
    </div>
  );
};
```

**💬 Explanation:**

- The input field is referenced using `useRef()`.
- `inputRef.current.focus()` accesses the DOM directly.
- No re-render is triggered when ref updates.

### 📝 Example 2 (Complex): Tracking Previous State Without Re-Renders

```jsx
import { useState, useEffect, useRef } from "react";

const CountTracker = () => {
  const [count, setCount] = useState(0);
  const prevCount = useRef();

  useEffect(() => {
    prevCount.current = count;
  }, [count]);

  return (
    <div>
      <p>Current: {count}</p>
      <p>Previous: {prevCount.current}</p>
      <button onClick={() => setCount(count + 1)}>Increase</button>
    </div>
  );
};
```

**💬 Explanation:**

- `prevCount.current` stores the previous count across renders.
- Updating the `ref` doesn’t trigger a re-render.
- Perfect for monitoring changes without disrupting the UI flow.

### ❌ Common Pitfalls

| ⚠️ Mistake                      | 💬 What Goes Wrong                                               |
| ------------------------------- | ---------------------------------------------------------------- |
| Expecting a re-render           | Changing `.current` doesn’t cause component to re-render         |
| Forgetting ref assignment       | Accessing `.current` before mounting results in `null`           |
| Using state where ref is better | Tracking mutable values with `useState()` can cause over-renders |

### 🧾 TL;DR – Quick Reference

| 🎯 Purpose             | ✅ Recommended Usage                                       |
| ---------------------- | ---------------------------------------------------------- |
| DOM access             | `const ref = useRef(null); ref.current.focus()`            |
| Persist across renders | `ref.current = value;` inside `useEffect()`                |
| Avoid re-renders       | Store timers, intervals, or previous state                 |
| Default value          | `useRef(initialValue)` returns `{ current: initialValue }` |

### 📌 Real-World Use Cases

- Managing uncontrolled inputs (e.g., forms without `useState()`)
- Tracking previous state or scroll position
- Accessing canvas or external library instances
- Storing timers, animation frames, and mutation observers

<br>

## 4. 🌍 React Context API – Say Goodbye to Prop Drilling

**🛠️ Introduction**

As your React app grows, you often need to pass data from a parent to deeply nested child components. Doing this via props can become painful—this is called **prop drilling**. React’s **Context API** solves this by enabling **global state sharing** without manually threading props through every level.

### 💡 Simple Analogy: A Public Bulletin Board

Instead of individually delivering notes to each office in a building, a company puts **one bulletin board in the lobby** where everyone can get the info. The Context API works like that—it provides a **single source of truth** for shared data across components.

### 📝 Example 1 (Simple): Theme Sharing Across Components

```jsx
import { createContext, useContext } from "react";

const ThemeContext = createContext("light");

const Header = () => {
  const theme = useContext(ThemeContext);
  return <h1 style={{ color: theme === "dark" ? "#fff" : "#000" }}>Hello!</h1>;
};

const App = () => {
  return (
    <ThemeContext.Provider value="dark">
      <Header />
    </ThemeContext.Provider>
  );
};
```

**💬 Explanation:**

- `createContext("light")` sets the default value.
- `ThemeContext.Provider` supplies a value (`"dark"`).
- Any component using `useContext(ThemeContext)` can access that value **directly, no prop passing required**.

### 📝 Example 2 (Complex): Auth State Across Multiple Components

```jsx
import { createContext, useContext, useState } from "react";

const AuthContext = createContext();

const LoginButton = () => {
  const { user, login } = useContext(AuthContext);
  return user ? <p>Welcome, {user}!</p> : <button onClick={login}>Log In</button>;
};

const AuthProvider = ({ children }) => {
  const [user, setUser] = useState(null);
  const login = () => setUser("Saief");
  return <AuthContext.Provider value={{ user, login }}>{children}</AuthContext.Provider>;
};

const App = () => (
  <AuthProvider>
    <LoginButton />
  </AuthProvider>
);
```

**💬 Explanation:**

- `AuthContext.Provider` shares both data (`user`) and actions (`login()`).
- `LoginButton` consumes them without any prop chaining.
- Makes **authentication globally accessible** while keeping logic encapsulated.

### ❌ Common Pitfalls

| 🧠 Misstep                     | ⚠️ Why It Hurts                                                 |
| ------------------------------ | --------------------------------------------------------------- |
| Using context without Provider | Results in `undefined` or default values                        |
| Overusing context              | Too many contexts can be hard to manage and maintain            |
| Updating deeply nested state   | Context updates cause **all consuming components to re-render** |
| Ignoring memoization           | Large contexts can impact performance without optimization      |

### 🧾 TL;DR – Quick Reference

| 📌 Task                   | ✅ Context API Usage                            |
| ------------------------- | ----------------------------------------------- |
| Create context            | `const MyContext = createContext(defaultValue)` |
| Provide value             | `<MyContext.Provider value={...}>...</>`        |
| Consume value in children | `const value = useContext(MyContext)`           |
| Share state & actions     | Provide `{ state, actions }` inside `value`     |

### 📌 Real-World Use Cases

- Global theme switching
- User authentication state
- Language or locale settings
- Feature flags and app-level toggles
- Sharing form or modal control state between sibling components

<br>

## 5. 🚀 Boosting React Performance with `React.memo()` & `useMemo()`

**🛠️ Introduction**

React re-renders components whenever state or props change. But sometimes, the re-renders happen even when the changes don’t affect a specific component. This can lead to wasted performance—especially in large lists or UI-heavy apps.

Two hooks solve this:

- `React.memo()` — prevents unnecessary re-rendering of functional components.
- `useMemo()` — caches expensive calculations so they don’t run on every render.

### 💡 Simple Analogy: Caching Answers Instead of Recalculating

Imagine you're taking a math test. If you already calculated $2 × 2 = 4$, do you need to recalculate it every time the teacher asks? Nope—you remember the answer and move on. That’s what memoization does: store computed results so React doesn’t waste time repeating them.

### 📝 Example 1 (Simple): Skipping Re-Renders with `React.memo()`

```jsx
import React from "react";

const Child = React.memo(({ count }) => {
  console.log("Child rendered");
  return <p>Child Count: {count}</p>;
});

const Parent = () => {
  const [count, setCount] = React.useState(0);
  const [text, setText] = React.useState("");

  return (
    <div>
      <Child count={count} />
      <button onClick={() => setCount(count + 1)}>Increase Count</button>
      <input onChange={(e) => setText(e.target.value)} value={text} />
    </div>
  );
};
```

**💬 Explanation:**

- The `Child` component will **only re-render when `count` changes**, thanks to `React.memo()`.
- Typing in the input **won’t re-render** `Child`, avoiding unnecessary updates.

### 📝 Example 2 (Complex): Caching Heavy Calculations with `useMemo()`

```jsx
import { useState, useMemo } from "react";

const ExpensiveComponent = () => {
  const [num, setNum] = useState(10);
  const [text, setText] = useState("");

  const squared = useMemo(() => {
    console.log("Calculating...");
    return num * num;
  }, [num]);

  return (
    <div>
      <p>Squared Value: {squared}</p>
      <input type="number" onChange={(e) => setNum(Number(e.target.value))} />
      <input onChange={(e) => setText(e.target.value)} value={text} placeholder="Type something..." />
    </div>
  );
};
```

**💬 Explanation:**

- The squaring logic is wrapped in `useMemo()`.
- **Typing text won’t trigger recalculation**, because text isn’t a dependency.
- This is useful when computations are **CPU intensive**, like sorting, filtering, or transforming large datasets.

### ❌ Common Pitfalls

| 🧱 Mistake                        | 💥 Why It’s a Problem                                               |
| --------------------------------- | ------------------------------------------------------------------- |
| Overusing memoization             | Memoizing everything can make code **harder to read and debug**     |
| Wrong dependencies in `useMemo()` | Causes **stale or incorrect cached values**                         |
| Misapplying `React.memo()`        | Doesn't help if component **always receives new props**             |
| Memoizing inline functions        | Inline props override memoization unless wrapped with `useCallback` |

### 🧾 TL;DR – Quick Reference

| ⚙️ Tool             | 📌 When to Use                                            |
| ------------------- | --------------------------------------------------------- |
| `React.memo()`      | Prevent re-rendering **when props don’t change**          |
| `useMemo()`         | Cache **expensive calculations** based on dependencies    |
| Dependency array    | Always include relevant values to avoid **stale results** |
| Avoid memo overkill | Only memoize **when performance impact is measurable**    |

### 🎯 Interview Insight

- Common question: “**How does `React.memo` help optimize performance?**” → It skips re-rendering if props haven’t changed.
- Scenario challenge:
- Bonus tip: Interviewers may ask: “**How would you optimize a slow filter/search on a large list?**” → Use `useMemo()` for filtered results.

### 📌 Real-World Use Cases

- Memoizing filtered/sorted data from large datasets
- Preventing re-renders in shared or deeply nested UI components
- Avoiding expensive recalculations in dashboards or visualizations
- Making animations and inputs smoother by reducing unnecessary renders

<br>

## 6. ⚙️ Optimizing Performance with `useCallback()` – Prevent Unnecessary Function Re-Creation

**🛠️ Introduction**

Every time a React component re-renders, **all functions defined inside it get re-created**, even if their logic hasn't changed. While harmless in small apps, this behavior can cause **performance bottlenecks** in larger UIs—especially when those functions are passed down to child components.

The `useCallback()` hook solves this by **memoizing functions**, ensuring they’re **only re-created when specific dependencies change**. It works beautifully with `React.memo()` to prevent unwanted child renders.

### 💡 Simple Analogy: Handing Someone Reusable Instructions

Imagine you're a manager giving instructions to a team. If you rewrite the same rules every morning, you're wasting time. Instead, you write them once and **reuse the same set until something changes**. That’s `useCallback()`—your **rule sheet** stays untouched unless necessary, reducing unnecessary overhead.

### 📝 Example 1 (Simple): Memoizing a Button Click Handler

```jsx
import { useState, useCallback } from "react";

const Counter = () => {
  const [count, setCount] = useState(0);

  const increment = useCallback(() => {
    setCount((prev) => prev + 1);
  }, []);

  return <button onClick={increment}>Count: {count}</button>;
};
```

**💬 Explanation:**

- `increment` stays **stable** across renders because dependencies (`[]`) don’t change.
- This function can now be passed to child components without causing unnecessary renders.

### 📝 Example 2 (Complex): Preventing Child Component Re-Renders

```jsx
import { useState, useCallback, memo } from "react";

const MemoChild = memo(({ onClick }) => {
  console.log("Child rendered");
  return <button onClick={onClick}>Click Me</button>;
});

const Parent = () => {
  const [count, setCount] = useState(0);
  const [text, setText] = useState("");

  const handleClick = useCallback(() => {
    setCount((prev) => prev + 1);
  }, []);

  return (
    <div>
      <MemoChild onClick={handleClick} />
      <input value={text} onChange={(e) => setText(e.target.value)} />
    </div>
  );
};
```

**💬 Explanation:**

- Typing in the input causes re-renders, but `MemoChild` doesn’t re-render.
- Thanks to `useCallback()`, `handleClick` maintains the same reference across renders, **preventing `MemoChild` from re-rendering unnecessarily**.

### ❌ Common Pitfalls

| 🧠 Gotcha                    | ⚠️ What Happens                                                             |
| ---------------------------- | --------------------------------------------------------------------------- |
| Omitting dependencies        | Function may use stale state or props                                       |
| Overusing `useCallback()`    | Adds unnecessary complexity—don’t memoize unless performance demands it     |
| Forgetting `React.memo()`    | Memoizing the function won't help if the child isn’t memoized               |
| Ignoring reference stability | If the memoized function depends on unstable objects, it'll still re-create |

### 🧾 TL;DR – Quick Reference

| 🔧 Scenario                       | ✅ Solution                              |
| --------------------------------- | ---------------------------------------- |
| Passing stable functions to child | Use `useCallback()` to memoize handlers  |
| Preventing re-renders in child    | Combine `useCallback()` + `React.memo()` |
| Trigger function on state update  | Add that state to the dependencies array |
| Avoid stale closures              | Always keep dependencies accurate        |

### 🎯 Interview Insight

- Expect questions like: “**Why would you use `useCallback()`?**” → To avoid creating new function instances on every render, especially when passing to memoized children.
- Common challenge:
- Bonus prompt: “**How does `useCallback()` differ from `useMemo()`?**” → `useMemo()` caches returned values, while `useCallback()` caches functions.

### 📌 Real-World Use Cases

- Optimizing performance in lists, tables, dropdowns, or card layouts
- Preventing re-renders in deeply nested components like modals or accordions
- Stabilizing event handlers passed into custom hooks or UI frameworks
- Reducing unnecessary renders in dashboards, editors, and filter-heavy UIs

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

- **`useFetch(url)` handles API calls**, making it **reusable for multiple components**.

- This **prevents repetitive logic**, improving **maintainability**.

- Any component using `useFetch()` **automatically gets loading state and data**, making it **simpler and more efficient**.

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

<br>
