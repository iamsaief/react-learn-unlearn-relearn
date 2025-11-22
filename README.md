<div align="center">
  <img height="80" src="https://upload.wikimedia.org/wikipedia/commons/a/a7/React-icon.svg" />
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

**🛠️ Introduction**

`useState()` is perfect for managing simple, isolated values. But once your component state becomes **structured, intertwined, or depends on conditional logic**, things can get messy fast.

Enter `useReducer()`—a hook that lets you define **state transitions as actions**, using **a centralized reducer function**. It’s a first step toward Redux-like architecture and an ideal tool for managing **forms, lists, UI flows, and complex interactions**.

### 💡 Simple Analogy: A Postal Sorting Machine vs Hand Delivering

Think of `useState()` like manually walking around and delivering each mail. It works for small offices. Now picture a **postal sorting machine (`useReducer()`) that automatically routes and dispatches mail** based on labels. You give it a command, and it handles the logic—fast, scalable, centralized.

### 📝 Example 1 (Practical): Managing a Multi-Field Form

**💼 Use Case:** You have a form with multiple fields—name, email, message. Rather than managing each with a separate `useState()`, you streamline it with `useReducer()`.

```jsx
const initialState = { name: "", email: "", message: "" };

function formReducer(state, action) {
  switch (action.type) {
    case "UPDATE_FIELD":
      return { ...state, [action.field]: action.value };
    case "RESET":
      return initialState;
    default:
      return state;
  }
}
```

```jsx
const ContactForm = () => {
  const [state, dispatch] = useReducer(formReducer, initialState);

  return (
    <form>
      <input
        name="name"
        value={state.name}
        onChange={(e) => dispatch({ type: "UPDATE_FIELD", field: "name", value: e.target.value })}
      />
      <input
        name="email"
        value={state.email}
        onChange={(e) => dispatch({ type: "UPDATE_FIELD", field: "email", value: e.target.value })}
      />
      <textarea
        name="message"
        value={state.message}
        onChange={(e) => dispatch({ type: "UPDATE_FIELD", field: "message", value: e.target.value })}
      />
      <button type="button" onClick={() => dispatch({ type: "RESET" })}>
        Clear
      </button>
    </form>
  );
};
```

**💬 Explanation:**

- You manage all fields inside a single object using a reducer.
- Adding new fields later is easy—no need to create more states.
- Actions (`UPDATE_FIELD`, `RESET`) describe intentions clearly.

### 📝 Example 2 (Scalable): Building a UI State Controller

**🧭 Use Case:** Managing UI component state (tabs, modals, loading state) where transitions follow structured actions.

```jsx
const initialState = { modalOpen: false, activeTab: "home", loading: false };

function uiReducer(state, action) {
  switch (action.type) {
    case "OPEN_MODAL":
      return { ...state, modalOpen: true };
    case "CLOSE_MODAL":
      return { ...state, modalOpen: false };
    case "SET_TAB":
      return { ...state, activeTab: action.payload };
    case "SET_LOADING":
      return { ...state, loading: action.payload };
    default:
      return state;
  }
}
```

```jsx
const Dashboard = () => {
  const [uiState, dispatch] = useReducer(uiReducer, initialState);

  return (
    <>
      <nav>
        <button onClick={() => dispatch({ type: "SET_TAB", payload: "settings" })}>Settings</button>
        <button onClick={() => dispatch({ type: "SET_TAB", payload: "profile" })}>Profile</button>
      </nav>

      <button onClick={() => dispatch({ type: "OPEN_MODAL" })}>Open Modal</button>

      {uiState.modalOpen && <div className="modal">Modal Content</div>}
      <p>Current Tab: {uiState.activeTab}</p>
    </>
  );
};
```

**💬 Explanation:**

- Each UI update is driven by an action.
- This keeps logic declarative and predictable.
- You can debug transitions easily or tie them into analytics events.

### ❌ Common Pitfalls

| ⚠️ Mistake                             | 💥 Why It’s a Problem                                                    |
| -------------------------------------- | ------------------------------------------------------------------------ |
| Using `useReducer()` for trivial state | Adds unnecessary complexity—stick to `useState()` for simple toggles     |
| Forgetting default return              | Reducer must return state even if action type isn't recognized           |
| Misusing `dispatch` outside logic      | Treating `dispatch()` like an updater function breaks action abstraction |
| Mutating state inside reducer          | Always return a **new state object** to preserve immutability            |

### 🧾 TL;DR – Quick Reference

| 🧠 Task                   | 🛠️ Reducer Strategy                                    |
| ------------------------- | ------------------------------------------------------ |
| Managing structured state | Use `useReducer()` with initial state and action types |
| Dispatching actions       | Call `dispatch({ type: "ACTION", payload })`           |
| Resetting state           | Add a `RESET` case or use your `initialState`          |
| Improving readability     | Give actions descriptive names—like `"OPEN_MODAL"`     |
| Scaling complexity        | Centralize reducer logic for global control            |

### 🎯 Interview Insight

- Typical question: “**When would you choose `useReducer()` over `useState()`?**” → When your state is **an object with multiple keys or has complex update logic**.
- Scenario challenge:
- Bonus point: Understanding how `useReducer()` scales lays the foundation for **state libraries** like Redux or Zustand.

### 📌 Real-World Use Cases

- Handling forms with multiple fields and reset logic
- Managing modal state, page flows, or tab navigation
- Driving global app state transitions with clean action types
- Refactoring messy `useState()` logic into predictable flow

<br>

## 8. 🔄 Creating Custom Hooks – Make Your React Code Reusable & Scalable

**🛠️ Introduction**

As your app grows, duplicated logic across components can become a nightmare—handling API calls, debouncing inputs, or managing form validations. **Custom hooks** offer a clean way to extract and reuse this logic by combining existing hooks (`useState`, `useEffect`, `useCallback`, etc.) into **self-contained, shareable functions.**

They help enforce **DRY principles**, **improve readability**, and ensure **business logic is modular**.

### 💡 Simple Analogy: Building a Multi-Purpose Toolkit

Instead of rewriting the same screwdriver for every use, you craft a **universal tool**—compact, reusable, and effective. Custom hooks are **your universal utilities**, helping any component access complex behaviors with just a line of code.

### 📝 Example 1: `useFetch()` – Simplify API Calls

**📦 Use Case**: Multiple components need to fetch data, handle loading, and error states. You create a generic `useFetch()` hook.

```jsx
import { useState, useEffect } from "react";

export const useFetch = (url) => {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState(null);

  useEffect(() => {
    if (!url) return; // Don’t run if URL is missing

    const controller = new AbortController(); // For cancelling fetch if unmounted
    const signal = controller.signal;

    const fetchData = async () => {
      setLoading(true); // Start loading
      setError(null); // Clear any previous error

      try {
        const response = await fetch(url, { signal });
        if (!response.ok) throw new Error("Network response was not ok");

        const json = await response.json();
        setData(json); // Save fetched data
      } catch (err) {
        if (err.name !== "AbortError") setError(err); // Ignore if fetch was cancelled
      } finally {
        setLoading(false); // Stop loading regardless of outcome
      }
    };

    fetchData();

    return () => controller.abort(); // Cleanup on unmount
  }, [url]);

  return { data, loading, error };
};
```

**💬 Explanation:**

1. `useEffect()` runs whenever the `url` changes.
2. An **AbortController** cancels the fetch if the component unmounts during loading—avoids memory leaks.
3. `fetchData()` uses `async/await` to clearly separate the fetch logic from error and cleanup handling.
4. All three pieces—**data, loading, and error**—are tracked independently for precise UI control.

### Example 2: ⏳ `useDebounce()` – Delay Execution Until User Stops Typing

```jsx
import { useState, useEffect } from "react";

export const useDebounce = (value, delay = 300) => {
  const [debounced, setDebounced] = useState(value);

  useEffect(() => {
    const timer = setTimeout(() => setDebounced(value), delay);

    return () => clearTimeout(timer); // Clear timer if value changes early
  }, [value, delay]);

  return debounced;
};
```

#### 🧪 Usage Example – Live Search

```jsx
import { useState } from "react";
import { useDebounce } from "./hooks/useDebounce";
import { useFetch } from "./hooks/useFetch";

const SearchBox = () => {
  const [query, setQuery] = useState("");
  const debouncedQuery = useDebounce(query, 500);
  const { data, loading, error } = useFetch(debouncedQuery ? `/api/search?q=${debouncedQuery}` : null);

  return (
    <>
      <input placeholder="Search..." value={query} onChange={(e) => setQuery(e.target.value)} />

      {loading ? (
        <p>Loading...</p>
      ) : error ? (
        <p>Oops! Something went wrong.</p>
      ) : data?.results?.length === 0 ? (
        <p>No results found.</p>
      ) : (
        <ul>
          {data?.results?.map((item) => (
            <li key={item.id}>{item.name}</li>
          ))}
        </ul>
      )}
    </>
  );
};
```

**💬 Explanation:**

1. As the user types in `query`, `useDebounce()` holds back updates until there's a **500ms pause**.
2. Every new keystroke **resets the timer**, preventing immediate API calls.
3. When the user stops typing, the debounced value is returned and used in the API request.
4. Prevents backend overload and improves user experience with smoother UI.

### Example 3: 🛞 `useThrottle()` – Limit Frequency of Updates

**🧠 Why:** Throttle limits execution to once every N milliseconds—perfect for scroll, resize, mouse move events.

```jsx
import { useState, useEffect } from "react";

export const useThrottle = (value, limit = 300) => {
  const [throttled, setThrottled] = useState(value);

  useEffect(() => {
    const timer = setTimeout(() => {
      setThrottled(value);
    }, limit);

    return () => clearTimeout(timer); // Clear on value change
  }, [value, limit]);

  return throttled;
};
```

#### 🧪 Usage Example – Scroll Tracker

```jsx
const [scrollY, setScrollY] = useState(0);
const throttledScroll = useThrottle(scrollY, 250);

useEffect(() => {
  const handleScroll = () => setScrollY(window.scrollY);
  window.addEventListener("scroll", handleScroll);
  return () => window.removeEventListener("scroll", handleScroll);
}, []);

return <div>Throttled Scroll Y: {throttledScroll}</div>;
```

**💬 Explanation:**

1. As the user scrolls, `scrollY` changes rapidly—possibly dozens of times per second.
2. `useThrottle()` enforces a **250ms delay**, so updates only occur **4 times per second**.
3. Great for performance-heavy components like animations, sticky headers, or analytics.

### 📦 Customs Hook Summary

| ⚒️ Hook Name    | 📌 Purpose                         | 💡 Ideal Use Case              |
| --------------- | ---------------------------------- | ------------------------------ |
| `useFetch()`    | API abstraction with loading/error | Product grids, article lists   |
| `useDebounce()` | Wait until user stops typing       | Search input, autosave         |
| `useThrottle()` | Limit update rate                  | Scroll tracking, resize events |

### ❌ Common Pitfalls

| 💥 Pitfall                  | ⚠️ Why It’s Problematic                                              |
| --------------------------- | -------------------------------------------------------------------- |
| Naming without `use` prefix | React won’t treat it as a hook—rules of hooks won't apply            |
| Ignoring hook dependencies  | `useEffect`, `useCallback`, etc. inside the hook need correct arrays |
| Overcomplicating early      | Don’t abstract logic until you’ve repeated it in at least 2 places   |
| Coupling too many concerns  | Each hook should do **one thing well** for reuse flexibility         |

### 🧾 TL;DR – Quick Reference

| 🧩 Situation                        | 🧪 Best Practice                                          |
| ----------------------------------- | --------------------------------------------------------- |
| Need shared logic across components | Extract into a custom hook                                |
| Centralizing API, forms, debouncing | Use existing hooks (`useEffect`, `useState`, etc.)        |
| Multiple responsibilities           | Split into smaller hooks (e.g., `useDebounce`, `useForm`) |
| Must start with `use` prefix        | Required for hook rules and linting                       |

### 🎯 Interview Insight

- Question you’ll hear: “**How do you refactor duplicate logic used in multiple components?**” → Create a custom hook using built-in React hooks.
- Follow-up challenge:
- **Pro move**: Bring up custom hooks when asked about **code scalability, testing**, or onboarding new team members.

### 📌 Real-World Use Cases

- Debouncing user input (`useDebounce`)
- Media query matching (`useMediaQuery`)
- Element visibility (`useOnScreen`, `useIntersectionObserver`)
- Scroll position tracking
- Form validation logic

<br>

## 9. 📤 Mastering React Portals – Rendering Outside the Main DOM

**🛠️ Introduction**

In traditional React, components render **inside the DOM hierarchy** of their parents. But what if you need an element (like a modal, tooltip, or dropdown) to break out of its container—for styling, positioning, or layering reasons? That’s where React Portals shine—they allow you to render components into a **different part of the DOM** while keeping React’s context and event handling intact.

### 💡 Simple Analogy: A VIP Balcony at a Concert

Most attendees sit inside the venue, but some VIPs access a **private balcony with a better view**. Portals are your balcony—they **render elsewhere**, away from the crowd, but they’re still part of the show (i.e., React tree).

### 📝 Example 1 (Real-World): Toggleable Modal with Close Button

```jsx
import ReactDOM from "react-dom";
import { useState } from "react";

const modalRoot = document.getElementById("modal-root");

const Modal = ({ children, onClose }) => {
  return ReactDOM.createPortal(
    <div style={styles.overlay}>
      <div style={styles.modal}>
        <button onClick={onClose}>Close</button>
        {children}
      </div>
    </div>,
    modalRoot
  );
};

const App = () => {
  const [open, setOpen] = useState(false);

  return (
    <>
      <button onClick={() => setOpen(true)}>Open Modal</button>
      {open && (
        <Modal onClose={() => setOpen(false)}>
          <p>Hello from modal!</p>
        </Modal>
      )}
    </>
  );
};

const styles = {
  overlay: {
    position: "fixed",
    top: 0,
    left: 0,
    right: 0,
    bottom: 0,
    backgroundColor: "rgba(0,0,0,0.5)",
    display: "flex",
    justifyContent: "center",
    alignItems: "center",
  },
  modal: {
    background: "#fff",
    padding: "20px",
    borderRadius: "8px",
  },
};
```

**🧠 Explanation:**

- When the "Open Modal" button is clicked, state updates to show the modal.
- The modal renders into the `modal-root`, avoiding any styling conflicts or z-index issues from `App`.
- Clicking “Close” calls `onClose()` which updates state and removes the modal.
- You now have a fully isolated, accessible, and responsive modal component.

### 📝 Example 3 (Real-World): Tooltip That Follows Hovered Element

```jsx
// Tooltip.jsx
import ReactDOM from "react-dom";

const tooltipRoot = document.getElementById("tooltip-root");

export const Tooltip = ({ position, text }) => {
  if (!position) return null;

  const style = {
    position: "fixed",
    top: position.y + 10,
    left: position.x + 10,
    background: "#333",
    color: "#fff",
    padding: "6px 10px",
    borderRadius: "4px",
    fontSize: "12px",
    pointerEvents: "none",
    zIndex: 9999,
  };

  return ReactDOM.createPortal(<div style={style}>{text}</div>, tooltipRoot);
};
```

```jsx
// HoverBox.jsx
import { useState } from "react";
import { Tooltip } from "./Tooltip";

const HoverBox = () => {
  const [tooltipPos, setTooltipPos] = useState(null);

  const handleMouseEnter = (e) => {
    const { clientX, clientY } = e;
    setTooltipPos({ x: clientX, y: clientY });
  };

  const handleMouseLeave = () => {
    setTooltipPos(null);
  };

  return (
    <div
      onMouseEnter={handleMouseEnter}
      onMouseLeave={handleMouseLeave}
      style={{ padding: "40px", border: "1px solid #ccc", display: "inline-block" }}
    >
      Hover me
      <Tooltip position={tooltipPos} text="Tooltip with portal magic ✨" />
    </div>
  );
};
```

```html
<!-- In public/index.html -->
<div id="root"></div>
<div id="tooltip-root"></div>
```

**🧠 Explanation:**

- **Separate container:** `<div id="tooltip-root" />` is created outside your main React root for tooltip rendering.
- **`Tooltip` component:** Uses `ReactDOM.createPortal()` to render into `tooltip-root`, ensuring it won't be clipped by overflowing parent containers.
- **Position tracking:** On hover, it captures `clientX` and `clientY` from the mouse event and positions the tooltip nearby.
- **Clean removal:** When hover ends, tooltip disappears instantly.

### ❌ Common Pitfalls

| 🧨 Problem                       | ⚠️ Why It Happens                                                                    |
| -------------------------------- | ------------------------------------------------------------------------------------ |
| Missing a portal DOM container   | Will throw an error or silently fail—must have **root** element (i.e., `modal-root`) |
| Not handling scroll locking      | Background content may scroll when modal is open                                     |
| Style conflicts from parent tree | Using normal rendering may apply `overflow: hidden` or clipping                      |
| Forgetting cleanup on unmount    | Ensure modals are removed cleanly on navigation or state change                      |

### 🧾 TL;DR – Quick Reference

| 🔧 Task                     | ✅ Best Practice                              |
| --------------------------- | --------------------------------------------- |
| Create portal               | Use `ReactDOM.createPortal(child, container)` |
| Place content outside root  | Add a DOM node like `<div id="modal-root" />` |
| Maintain React tree context | Portals preserve props and context naturally  |
| Common use cases            | Modals, tooltips, dropdowns, floating menus   |

### 🎯 Interview Insight

- You might be asked: “**How would you render a modal that’s not affected by its parent’s overflow styles?**” → Answer: Use React Portals and render to a sibling DOM node.
- Practical test:
- Bonus concept: Portals maintain **event bubbling and React context**, unlike `window.appendChild()` or vanilla JS DOM manipulation.

### 📌 Real-World Use Cases

- Modals that escape container boundaries
- Toast notifications fixed to screen corners
- Dropdowns inside tables or containers
- Tooltips with custom positioning behavior
- Multi-layered UI components (sidebars, banners)

<br>

## 10. ⚡ Unlocking Concurrent Rendering – Making React Apps Faster & Smoother

**🛠️ Introduction**

In traditional rendering, React blocks the UI until each update completes. For small components, this is fine—but in large UIs, this can cause **noticeable lag**, especially when processing filters, animations, or large datasets.

**Concurrent Rendering** (available starting React 18) lets React **pause rendering**, **prioritize urgent updates** like user input, and **resume work later**—so your interface stays buttery smooth.

### 💡 Simple Analogy: Coffee While Waiting for Lunch

Imagine you order lunch at a café—it’ll take time. But while you wait, the barista hands you coffee immediately. React does the same with concurrent rendering—it gives **priority to quick updates** (like typing) and **defers heavier ones** like rendering 1,000 items.

### 📝 Example 1 (Practical): Using `startTransition()` for Prioritized Updates

```jsx
import { useState, startTransition } from "react";

const SearchBox = ({ items }) => {
  const [query, setQuery] = useState("");
  const [filtered, setFiltered] = useState(items);

  const handleChange = (e) => {
    const value = e.target.value;
    setQuery(value);

    startTransition(() => {
      const results = items.filter((item) => item.name.toLowerCase().includes(value.toLowerCase()));
      setFiltered(results);
    });
  };

  return (
    <>
      <input value={query} onChange={handleChange} />
      <ul>
        {filtered.map((item) => (
          <li key={item.id}>{item.name}</li>
        ))}
      </ul>
    </>
  );
};
```

**🧠 Explanation:**

- `query` updates immediately for responsive typing.
- `startTransition()` wraps the filtering logic—React treats this update as non-urgent.
- If the user types again quickly, React **may delay or skip previous** filters to preserve UI fluidity.
- Useful in lists, dashboards, or search-heavy views.

### 📝 Example 2 (Real-World): Using `useTransition()` to Show Pending State

```jsx
import { useState, useTransition } from "react";

const LiveSearch = ({ dataset }) => {
  const [term, setTerm] = useState("");
  const [results, setResults] = useState([]);
  const [isPending, startTransition] = useTransition();

  const handleInput = (e) => {
    const value = e.target.value;
    setTerm(value);

    startTransition(() => {
      const filtered = dataset.filter((item) => item.title.toLowerCase().includes(value.toLowerCase()));
      setResults(filtered);
    });
  };

  return (
    <>
      <input value={term} onChange={handleInput} />
      {isPending && <p>Updating results…</p>}
      <ul>
        {results.map((r) => (
          <li key={r.id}>{r.title}</li>
        ))}
      </ul>
    </>
  );
};
```

**🧠 Explanation:**

- `useTransition()` provides `isPending`, a flag that indicates React is processing a transition.
- While the search updates, you show a loading message, but **UI remains interactive**.
- Eliminates jank without blocking input.

### ❌ Common Pitfalls

| ⚠️ Mistake                            | 🧨 Why It Backfires                                                   |
| ------------------------------------- | --------------------------------------------------------------------- |
| Wrapping urgent updates in transition | Delays critical actions like button clicks or form submission         |
| Using transitions for animations      | These are best handled by requestAnimationFrame—not React transitions |
| Ignoring user feedback                | Forgetting `isPending` makes it hard to show transitions or loading   |

### 🧾 TL;DR – Quick Reference

| 🧩 Scenario                    | ✅ Strategy                                     |
| ------------------------------ | ----------------------------------------------- |
| Heavy UI updates               | Wrap in `startTransition()`                     |
| Show spinner during transition | Use `useTransition()` and show `isPending`      |
| Prioritize text input          | Update input outside transition, defer the rest |
| Avoid blocking interactions    | Transitions keep React responsive during work   |

### 🎯 Interview Insight

- Common question: “**What does concurrent rendering mean in React?**” → React can **pause, interrupt, and prioritize** rendering to keep UIs fast.
- Challenge prompt:
- Smart follow-up: “**When would you NOT use a transition?**” → For updates that need to happen instantly (e.g. navigation, submit actions).

### 📌 Real-World Use Cases

- Dashboards with filters, charts, and large datasets
- Search inputs on media-heavy platforms
- Multi-step forms with validation and async state
- Chat UIs that fetch messages but prioritize typing

<br>
