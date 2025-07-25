<div align="center">
  <img height="80" src="https://svgmix.com/uploads/e86a0a-react.svg">
  <h1>রিএক্টঃ শিখুন-ভুলুন-আবার শিখুন ⚛️</h1>
</div>

আপনার **রিএক্ট দক্ষতা পরীক্ষা করুন**, গুরুত্বপূর্ণ ধারণাগুলি পুনঃজীবিত করুন, অথবা **ইন্টারভিউয়ের জন্য প্রস্তুতি নিন!** 💪 এই **সম্পূর্ণ ডকুমেন্ট গাইড** আপনাকে **রিএক্ট-এর গভীর বিষয়গুলি পরিষ্কারভাবে শেখাতে** সাহায্য করবে, যেখানে রয়েছে **বিশদ ব্যাখ্যা, একাধিক উদাহরণ, সাধারণ ভুলত্রুটি এবং বাস্তব জীবনের প্রয়োগ**।

আমি এটি নিজের **শিখন ও অবসরে আনন্দের জন্য তৈরি করেছি**, তাই **যদি কোনো ভুল থেকে থাকে, দয়া করে ক্ষমা করবেন**। 😊 আপনি যদি এটি **উপকারী মনে করেন**, তাহলে **⭐️ দিয়ে সাহায্য করুন বা রেফারেন্স দিন**, এটি আমাকে আরও ভালো করতে অনুপ্রেরণা দেবে!

আপনার **প্রোগ্রামিং যাত্রায় শুভকামনা—** 🙏✨ হ্যাপি কোডিং! 🧑‍💻

<p align="center">
💬 যদি আমার সাথে যোগাযোগ করতে চান, ↩️ <br/>
<a href="https://www.facebook.com/saiefalemon">Facebook</a> | <a href="https://www.linkedin.com/in/saiefalemon">LinkedIn</a> | <a href="https://www.iamsaief.com/">Blog</a>

---

**🗂️ সূচিপত্র:**

- [১. ⚡ `useEffect()` মাস্টারি – React-এর Side Effect Powerhouse](#১--useeffect-মাস্টারি--react-এর-side-effect-powerhouse)
- [২. 📜 `useState()` ব্যাখ্যা – কম্পোনেন্ট স্টেট সহজে ম্যানেজ করা](#২--usestate-ব্যাখ্যা--কম্পোনেন্ট-স্টেট-সহজে-ম্যানেজ-করা)
- [৩. 🔍 `useRef()` এর ব্যবহার – DOM অ্যাক্সেস করা রি-রেন্ডার ছাড়াই](#৩--useref-এর-ব্যবহার--dom-অ্যাক্সেস-করা-রি-রেন্ডার-ছাড়াই)
- [৪. 🌍 React Context API – Prop Drilling সমস্যার সমাধান](#৪--react-context-api--prop-drilling-সমস্যার-সমাধান)
- [৫. 🚀 `React.memo()` এবং `useMemo()` ব্যবহার করে React পারফরম্যান্স উন্নত করা](#৫--reactmemo-এবং-usememo-ব্যবহার-করে-react-পারফরম্যান্স-উন্নত-করা)
- [৬. ⚙️ `useCallback()` ব্যবহার করে পারফরম্যান্স অপ্টিমাইজ করা – অপ্রয়োজনীয় ফাংশন রিক্রিয়েশন প্রতিরোধ](#৬-️-usecallback-ব্যবহার-করে-পারফরম্যান্স-অপ্টিমাইজ-করা--অপ্রয়োজনীয়-ফাংশন-রিক্রিয়েশন-প্রতিরোধ)
- [৭. 🔁 `useReducer()` বনাম `useState()` – জটিল স্টেট পরিচালনা করার মাস্টারক্লাস](#৭--usereducer-বনাম-usestate--জটিল-স্টেট-পরিচালনা-করার-মাস্টারক্লাস)
- [৮. 🔄 কাস্টম Hooks তৈরি করা – React কোড পুনঃব্যবহারযোগ্য ও স্কেলেবল করা](#৮--কাস্টম-hooks-তৈরি-করা--react-কোড-পুনঃব্যবহারযোগ্য-ও-স্কেলেবল-করা)
- [৯. 📤 React Portals মাস্টার করা – মূল DOM-এর বাইরে কম্পোনেন্ট রেন্ডার করা](#৯--react-portals-মাস্টার-করা--মূল-dom-এর-বাইরে-কম্পোনেন্ট-রেন্ডার-করা)
- [১০. ⚡ Concurrent Rendering আনলক করা – React অ্যাপ আরও দ্রুত ও স্মুথ করা](#১০--concurrent-rendering-আনলক-করা--react-অ্যাপ-আরও-দ্রুত-ও-স্মুথ-করা)

---

## ১. ⚡ `useEffect()` মাস্টারি – React-এর Side Effect Powerhouse

**🛠️ পরিচিতি**

React এর `useEffect()` হুক ব্যবহার করে ফাংশনাল কম্পোনেন্টে **side effects** হ্যান্ডেল করা যায়। যেমন: ডেটা ফেচ করা, DOM আপডেট করা, বা ইভেন্ট সাবস্ক্রাইব করা। এটা `componentDidMount()` আর `componentDidUpdate()` এর কাজকে আরও সহজ আর এক জায়গায় নিয়ে এসেছে।

### 💡 সহজ উদাহরণ: টাইমার দিয়ে রান্না

ভাবো React তোমার কম্পোনেন্টকে রান্নার মতো রেন্ডার করছে। কিছু কাজ যেমন পানি ফুটানো, রান্নার পর করতে হয়। `useEffect()` ঠিক টাইমারের মতো কাজ করে — রান্নার (রেন্ডারিং) পর কাজ চালায়, আর শেষে চুলা বন্ধ করার মতো ক্লিনআপও করতে দেয়।

### 📝 উদাহরণ ১ (সহজ): কম্পোনেন্ট মাউন্ট হলে API থেকে ডেটা আনা

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

**💬 ব্যাখ্যা ধাপে ধাপে:**

- `useEffect()` কম্পোনেন্ট রেন্ডারের পরে চলে।
- ফাঁকা dependency array `[]` দিলে এটা একবারই চলে — `componentDidMount()` এর মতো।
- ডেটা ফেচ হয়, state সেট হয়, তারপর কম্পোনেন্ট আবার রেন্ডার হয় নতুন ডেটা নিয়ে।

### 📝 উদাহরণ ২ (জটিল): ইভেন্ট লিসেনার অ্যাড ও ক্লিনআপ

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

**💬 ব্যাখ্যা ধাপে ধাপে:**

- যখন কম্পোনেন্ট মাউন্ট হয়, ইভেন্ট লিসেনার অ্যাড হয়।
- যখন আনমাউন্ট হয়, ক্লিনআপ ফাংশন দিয়ে লিসেনার রিমুভ হয়।
- এতে মেমোরি লিক বা এক্সট্রা ইভেন্ট অ্যাটাচ হওয়ার ঝামেলা হয় না।

### ❌ সাধারণ ভুলগুলো

| 🚩 সমস্যা                     | 😵 কী ধরনের সমস্যা হয়                                       |
| ----------------------------- | ----------------------------------------------------------- |
| 🔁 dependency array না থাকা   | প্রতি রেন্ডারে effect চলে, ফলে ইনফিনিট লুপ হতে পারে         |
| 🧼 ক্লিনআপ বাদ দেওয়া          | মেমোরি লিক হয়, পুরনো লিসেনার বা টাইমার থেকে যায়             |
| ⚡ বেশি `useEffect()` ব্যবহার | অনেক লজিক এক জায়গায় থাকলে কোড বোঝা আর মেইন্টেইন করা কঠিন হয় |
| 🔄 dependency ভুল দেওয়া       | পুরনো ডেটা দেখায় বা অদ্ভুত আচরণ করে                         |

### 🧾 সংক্ষিপ্ত রেফারেন্স

| 📍 কী করতে চাও                     | ✅ কীভাবে করবে                          |
| ---------------------------------- | --------------------------------------- |
| শুধু একবার চালাতে চাও              | `useEffect(() => {...}, [])`            |
| state চেঞ্জে চালাতে চাও            | `useEffect(() => {...}, [stateVar])`    |
| আনমাউন্টে ক্লিনআপ করতে চাও         | `useEffect()` এর ভেতর ফাংশন রিটার্ন করো |
| একাধিক ভ্যারিয়েবল ট্র্যাক করতে চাও | `useEffect(() => {...}, [a, b, c])`     |

### 📌 বাস্তব উদাহরণ

- কম্পোনেন্ট লোড হলে API থেকে ডেটা আনা
- WebSocket বা Firebase সাবস্ক্রাইব/আনসাবস্ক্রাইব করা
- DOM ম্যানিপুলেশন (যেমন scroll বা resize)
- পেজ ভিজিট ট্র্যাক করা, analytics চালানো
- setInterval বা setTimeout হ্যান্ডেল করা

<br>

## ২. 📜 `useState()` ব্যাখ্যা – কম্পোনেন্ট স্টেট সহজে ম্যানেজ করা

**🛠️ পরিচিতি**

React কম্পোনেন্টকে ডাইনামিক করার জন্য state দরকার হয়। আগে class কম্পোনেন্টে `this.state` ব্যবহার করতে হতো। এখন `useState()` দিয়ে **functional component** এর ভিতরে **value ট্র্যাক ও আপডেট** করা যায় খুব সহজে। এটা লোকাল ডেটা ম্যানেজ করার জন্য সবচেয়ে গুরুত্বপূর্ণ হুক।

### 💡 সহজ উদাহরণ: স্টিকি নোট ব্যবহার

ভাবো তুমি ডেস্কে কাজ করছো আর স্টিকি নোটে টুকটাক জিনিস লিখে রাখছো — সহজে এডিট, রিপ্লেস বা রিমুভ করা যায়। `useState()` ঠিক এভাবেই কম্পোনেন্টে কিছু স্টোর করে (যেমন count), আপডেট করে আর UI রি-রেন্ডার করে।

### 📝 উদাহরণ ১ (সহজ): Counter তৈরি করা

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

**💬 ব্যাখ্যা:**

- `useState(0)` দিয়ে `count` নামের state তৈরি হয় আর `setCount` ফাংশন দিয়ে এটা আপডেট করা যায়।
- যখনই `setCount()` কল করা হয়, React আবার কম্পোনেন্ট রেন্ডার করে নতুন মান নিয়ে।

### 📝 উদাহরণ ২ (জটিল): Form Input ম্যানেজ করা

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

**💬 ব্যাখ্যা:**

- শুধু প্রিমিটিভ ভ্যালু না, `useState()` দিয়ে **অবজেক্টও** ম্যানেজ করা যায়।
- `handleChange` ফাংশন পুরো state না বদলে শুধু যেটা দরকার সেটাই আপডেট করে।

### 📝 উদাহরণ ৩: অ্যাসিনক্রোনাস স্টেট আপডেট

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

**💬 ব্যাখ্যা:**

- ২ সেকেন্ড পর state আপডেট হয়, যেটা বাস্তবে API থেকে ডেটা আসার মতো কাজ করে।

### ❌ সাধারণ ভুলগুলো

| 🚩 সমস্যা                   | 😵 কী ধরনের সমস্যা হয়                                                      |
| --------------------------- | -------------------------------------------------------------------------- |
| 🛑 state ডিরেক্টলি পরিবর্তন | `count = count + 1` করলে রি-রেন্ডার হয় না — সবসময় `setState()` ব্যবহার করো |
| 🔁 অ্যাসিনক্রোনাস আপডেট     | একাধিক `setState` একসাথে দিলে তা সাথে সাথে reflect নাও করতে পারে           |
| 💡 immutability না মানা     | nested state ঠিকভাবে না আপডেট করলে ডেটা হারিয়ে যেতে পারে                   |

### 🧾 সংক্ষিপ্ত রেফারেন্স

| 🧩 প্যাটার্ন         | 💬 কাজ কী করে                                           |
| -------------------- | ------------------------------------------------------- |
| `useState(default)`  | রিয়্যাকটিভ স্টেট ভ্যারিয়েবল তৈরি করে                    |
| `setState(newValue)` | নতুন মান দিয়ে কম্পোনেন্ট রি-রেন্ডার করে                 |
| অবজেক্ট ম্যানেজ করা  | `{ ...prev, key: value }` দিয়ে নির্দিষ্ট অংশ আপডেট করা  |
| অ্যারে ম্যানেজ করা   | `[...prev, newItem]` দিয়ে নতুন আইটেম অ্যাড বা আপডেট করা |

### 📌 বাস্তব উদাহরণ

- ইউজার interaction ট্র্যাক করা (যেমন ক্লিক, ট্যাব, টগল)
- form input আর validation ম্যানেজ করা
- modal খোলা/বন্ধ অবস্থার state রাখা
- লোকাল প্রেফারেন্স যেমন থিম বা ফিল্টার সংরক্ষণ করা

<br>

## ৩. 🔍 `useRef()` এর ব্যবহার – DOM অ্যাক্সেস করা রি-রেন্ডার ছাড়াই

**🛠️ পরিচিতি**

`useRef()` এমন একটি হুক যা দিয়ে তুমি **mutable মান** স্টোর করতে পারো যা রেন্ডারের পরও থাকে, কিন্তু কম্পোনেন্ট রি-রেন্ডার করে না। সাধারণভাবে এটি ব্যবহৃত হয়:

- **সরাসরি DOM অ্যাক্সেস করতে**
- **কোনো মান ট্র্যাক করতে, আপডেট ছাড়াই**
- **টাইমার, আগের স্টেট, বা এক্সটার্নাল লাইব্রেরির রেফারেন্স রাখতে**

### 💡 সহজ উদাহরণ: বইয়ের বুকমার্ক

ভাবো তুমি একটা পাতায় বুকমার্ক রেখেছো—তুমি বই খুলো বা বন্ধ করো, সেটা একই জায়গায় থাকে। `useRef()` ও ঠিক তেমন — **একটি মানের সঙ্গে স্থায়ীভাবে সংযোগ রাখে** কিন্তু UI তে কিছু পরিবর্তন করে না (রি-রেন্ডার হয় না)।

### 📝 উদাহরণ ১ (সহজ): ইনপুট ফিল্ডে ফোকাস করা

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

**💬 ব্যাখ্যা:**

- `useRef()` দিয়ে ইনপুট ফিল্ড রেফারেন্স করা হয়।
- `inputRef.current.focus()` দিয়ে DOM-এ সরাসরি অ্যাক্সেস করা হয়।
- ref আপডেট হলেও রেন্ডার হয় না।

### 📝 উদাহরণ ২ (জটিল): আগের স্টেট ট্র্যাক করা রি-রেন্ডার ছাড়া

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

**💬 ব্যাখ্যা:**

- `prevCount.current` আগের `count` ধরে রাখে, রেন্ডারের পরেও।
- `.current` আপডেট করলেও কম্পোনেন্ট রেন্ডার হয় না।
- UI ব্যাঘাত না ঘটিয়ে ভ্যালু ট্র্যাক করতে উপযোগী।

### ❌ সাধারণ ভুলগুলো

| ⚠️ ভুল                         | 💬 কী সমস্যা হয়                                                  |
| ------------------------------ | ---------------------------------------------------------------- |
| রেন্ডার আশা করা                | `.current` বদলালেও কম্পোনেন্ট রেন্ডার হয় না                      |
| ref অ্যাসাইন করতে ভুলে যাওয়া   | মাউন্ট হওয়ার আগে `.current` অ্যাক্সেস করলে `null` পাওয়া যায়      |
| ref না ব্যবহার করে state নেওয়া | `useState()` দিয়ে mutable মান ট্র্যাক করলে বেশি রেন্ডার হতে পারে |

### 🧾 সংক্ষিপ্ত রেফারেন্স

| 🎯 উদ্দেশ্য             | ✅ কীভাবে ব্যবহার করবে                                         |
| ----------------------- | -------------------------------------------------------------- |
| DOM অ্যাক্সেস           | `const ref = useRef(null); ref.current.focus()`                |
| রেন্ডার পেরিয়ে মান রাখা | `ref.current = value;` এটা `useEffect()` এর ভিতরে করো          |
| রি-রেন্ডার এড়িয়ে চলা    | টাইমার, আগের স্টেট বা interval/stored ভ্যালু স্টোর করতে পারো   |
| ডিফল্ট মান              | `useRef(initialValue)` রিটার্ন করে `{ current: initialValue }` |

### 📌 বাস্তব উদাহরণ

- uncontrolled ইনপুট ম্যানেজ করা (যেমন `useState()` ছাড়া ফর্ম)
- আগের স্টেট বা স্ক্রল পজিশন ট্র্যাক করা
- canvas বা বাইরের লাইব্রেরি অ্যাক্সেস করা
- টাইমার, animation frame বা mutation observer রাখা

<br>

## ৪. 🌍 React Context API – Prop Drilling সমস্যার সমাধান

**🔹 ভূমিকা**

React Context API **prop drilling সমস্যার সমাধান করে**, যেখানে ডা**টা একাধিক লেয়ার গভীরে পাঠাতে হয়** props ব্যবহার করে। একাধিক কম্পোনেন্টের মধ্য দিয়ে props পাঠানোর পরিবর্তে, Context API **একটি গ্লোবাল স্টেট প্রদান করে, যা যেকোনো কম্পোনেন্ট ব্যবহার করতে পারে**।

### 💡 সহজ উদাহরণ: একটি পাবলিক বুলেটিন বোর্ড

একটি বিল্ডিংয়ের **প্রত্যেক ব্যক্তিকে আলাদাভাবে বার্তা পাঠানোর পরিবর্তে**, একটি **বুলেটিন বোর্ড** সবাইকে তথ্য শেয়ার করতে সাহায্য করে। একইভাবে, React Context API **ডাটাকে গ্লোবালি শেয়ার করে**, যা **গভীর props চেইন এড়াতে সাহায্য করে**।

### 📝 উদাহরণ ১: একটি থিম কনটেক্সট তৈরি করা

```jsx
import { createContext } from "react";

const ThemeContext = createContext("light");

const App = () => (
  <ThemeContext.Provider value="dark">
    <ChildComponent />
  </ThemeContext.Provider>
);
```

**💡 ব্যাখ্যা:**

- `createContext()` **একটি গ্লোবাল থিম ইনিশিয়ালাইজ করে**।

- `Provider` **চাইল্ড কম্পোনেন্টগুলোকে ঘিরে রাখে**, যা তাদের **থিম ভ্যালু (dark) অ্যাক্সেস করতে দেয়**।

**📌 সাধারণ ভুল**: কম্পোনেন্টগুলোকে **Provider দিয়ে না মোড়ানো**, যার ফলে `undefined` **কনটেক্সট মান পাওয়া যেতে পারে**।

### 📝 উদাহরণ ২: কনটেক্সট কম্পোনেন্টে ব্যবহার করা

```jsx
import { useContext } from "react";

const theme = useContext(ThemeContext);
return <div style={{ backgroundColor: theme === "dark" ? "#333" : "#fff" }}>থিম: {theme}</div>;
```

**💡 ব্যাখ্যা:**

- `useContext(ThemeContext)` নিকটবর্তী প্রদত্ত মান নেয়, যা **ম্যানুয়ালি props পাঠানো থেকে মুক্তি দেয়**।

### 📌 বাস্তব জীবনে কোথায় ব্যবহার হয়

- **Authentication state পরিচালনা**
- **থিম পরিবর্তন ও ইউজার প্রেফারেন্স**
- **মাল্টি-ল্যাঙ্গুয়েজ সাপোর্ট ব্যবস্থাপনা**

<br>

## ৫. 🚀 `React.memo()` এবং `useMemo()` ব্যবহার করে React পারফরম্যান্স উন্নত করা

**🔹 ভূমিকা**

React-এ স্টেট বা **props পরিবর্তিত হলে কম্পোনেন্ট পুনরায় রেন্ডার করে**, কিন্তু কখনো কখনো **এই রি-রেন্ডারিং অপ্রয়োজনীয় হয়ে** যায়। `React.memo()` এবং `useMemo()`**অপ্রয়োজনীয় পুনঃগণনা এড়িয়ে পারফরম্যান্স অপ্টিমাইজ করে**।

### 💡 সহজ উদাহরণ: পুনরায় নোট লেখার পরিবর্তে চিট শিট ব্যবহার

Memoization **পূর্বে গণনা করা মান সংরক্ষণ করে**, যাতে **পুনরায় একই হিসাব করতে না হয়**। এটি **চিট শিটে উত্তর লিখে রাখা**-এর মতো, যেখানে **প্রতিবার নতুন করে সমস্যা সমাধান করার দরকার হয় না**।

### 📝 উদাহরণ ১: `React.memo()` ব্যবহার করে অপ্রয়োজনীয় রি-রেন্ডার প্রতিরোধ

```jsx
import React from "react";

const MemoizedComponent = React.memo(({ count }) => <div>Count: {count}</div>);
```

**💡 ব্যাখ্যা:**

- `React.memo()` নিশ্চিত করে **এই কম্পোনেন্ট শুধুমাত্র `count` পরিবর্তিত হলে রেন্ডার হয়**, যা **অপ্রয়োজনীয় আপডেট কমায়**।

**📌 সাধারণ ভুল:** `React.memo()` **পরিবর্তিত চাইল্ড এলিমেন্টের ক্ষেত্রে ব্যবহার করা**, যা **অপ্রত্যাশিত রেন্ডারিং সমস্যা তৈরি করতে পারে**।

### 📝 উদাহরণ ২: `useMemo()`ব্যবহার করে ব্যয়বহুল গণনা অপ্টিমাইজ করা

```jsx
import { useMemo, useState } from "react";

const ExpensiveCalculation = ({ num }) => {
  const squaredNumber = useMemo(() => num * num, [num]);

  return <p>Squared: {squaredNumber}</p>;
};
```

**💡 ব্যাখ্যা:**

- `useMemo()`**গণনা করা মান ক্যাশ করে**, যেন **প্রত্যেক রেন্ডারে পুনরায় গণনা করার প্রয়োজন না হয়**।

### 📌 বাস্তব জীবনে কোথায় ব্যবহার হয়

- **বড় তালিকা বা জটিল গণনা অপ্টিমাইজ করতে**
- **অপ্রয়োজনীয় কম্পোনেন্ট রি-রেন্ডার প্রতিরোধ করতে**
- **UI-ভারী অ্যাপে ল্যাগ কমাতে**

<br>

## ৬. ⚙️ `useCallback()` ব্যবহার করে পারফরম্যান্স অপ্টিমাইজ করা – অপ্রয়োজনীয় ফাংশন রিক্রিয়েশন প্রতিরোধ

**🛠️ ভূমিকা**

প্রত্যেকবার **React কম্পোনেন্ট পুনরায় রেন্ডার হলে**, এর ভেতরে ঘোষিত **ফাংশনগুলো পুনরায় তৈরি হয়**। বেশিরভাগ ক্ষেত্রে এটি সমস্যা নয়, কিন্তু যদি **এই ফাংশনগুলো চাইল্ড কম্পোনেন্টে পাঠানো হয়**, তাহলে **অপ্রয়োজনীয় পুনঃসৃষ্টি পারফরম্যান্স সমস্যার কারণ হতে পারে**।

`useCallback()` ফাংশনগুলোকে **মেমোরাইজ করে**, যাতে সেগুলো **প্রয়োজন অনুযায়ী পুনরায় তৈরি হয়**।

### 💡 সহজ উদাহরণ: রান্নার রেসিপি লিখে সংরক্ষণ করা

ধরো তুমি **কাউকে পাস্তা রান্না শেখাচ্ছো**। প্রতিবার **নতুন করে রেসিপি বোঝানোর পরিবর্তে**, তুমি **একবার লিখে রাখো**, যেন তারা **প্রয়োজনমতো রেফার করতে পারে**।

একইভাবে, `useCallback()` **ফাংশন মেমোরিতে সংরক্ষণ করে**, React-কে **বারবার সেগুলো পুনরায় তৈরি করা থেকে বিরত রাখে**।

### 📝 উদাহরণ ১: `useCallback()` ব্যবহার করে ক্লিক হ্যান্ডলার মেমোরাইজ করা

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

**💡 ব্যাখ্যা:**

- `useCallback(() => setCount(prevCount + 1), [])` **নিশ্চিত করে ফাংশনটি শুধুমাত্র একবার তৈরি হবে**, প্রত্যেকবার পুনরায় তৈরি হবে না।

- `useCallback()` ছাড়া **React প্রতিবার `increment()` পুনরায় তৈরি করত**, যা **অপ্টিমাল নয়**।

### 📝 উদাহরণ ২: `useCallback()` ব্যবহার করে চাইল্ড কম্পোনেন্টের অপ্রয়োজনীয় রি-রেন্ডারিং প্রতিরোধ

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

**💡 ব্যাখ্যা:**

- `Child` কম্পোনেন্ট `memo()` দিয়ে মোড়ানো, যাতে এটি **শুধুমাত্র props পরিবর্তিত হলে পুনরায় রেন্ডার হয়**।
- **`useCallback()` ছাড়া `handleClick()` প্রতিবার পুনরায় তৈরি হতো**, ফলে `Child` **অপ্রয়োজনীয়ভাবে পুনরায় রেন্ডার হতো**।

**📌 সাধারণ ভুল:** অপ্রয়োজনীয়ভাবে **প্রতিটি ফাংশনের জন্য `useCallback()` ব্যবহার করা**, যা **কোড অপ্রয়োজনীয়ভাবে জটিল করে**।

### 📌 বাস্তব জীবনে কোথায় ব্যবহার হয়

- **লিস্ট রেন্ডারিং অপ্টিমাইজ করতে যখন চাইল্ডে কলব্যাক পাঠানো হয়**
- **ভারী UI ইন্টারঅ্যাকশনের সময় অপ্রয়োজনীয় রি-রেন্ডার প্রতিরোধ করতে**
- **ইভেন্ট হ্যান্ডলারের মধ্যে ব্যয়বহুল গণনা কমাতে**

<br>

## ৭. 🔁 `useReducer()` বনাম `useState()` – জটিল স্টেট পরিচালনা করার মাস্টারক্লাস

**🧩 ভূমিকা**

`useState()` **সাধারণ স্টেট আপডেটের জন্য ভালো**, কিন্তু যখন **স্টেট ট্রানজিশন জটিল হয়ে যায়**, তখন এটি **অব্যবস্থাপনা ও অদক্ষতা সৃষ্টি করতে পারে**—বিশেষ করে যখন **একাধিক স্টেট ভ্যালু পরস্পরের উপর নির্ভরশীল**।

React-এর `useReducer()` **একটি কাঠামোবদ্ধ পদ্ধতি প্রদান করে**, যেখানে **একটি পিওর ফাংশন (reducer) স্টেট আপডেট পরিচালনা করে প্রতিটি অ্যাকশন অনুযায়ী**।

এটি **Redux-এর মতো**, যেখানে স্টেট সরাসরি পরিবর্তনের পরিবর্তে **অ্যাকশন ডিসপ্যাচ করা হয়**, এবং **reducer সিদ্ধান্ত নেয় স্টেট কীভাবে পরিবর্তিত হবে**।

### 💡 সহজ উদাহরণ: একটি মেইল বাছাই করার সিস্টেম

`useState()` ব্যবহার করলে, তুমি **প্রত্যেকটি চিঠি একে একে হাতে বাছাই করো**। `useReducer()` ব্যবহার করলে, **একটি মেইল সিস্টেম স্বয়ংক্রিয়ভাবে চিঠি বাছাই ও প্রক্রিয়া করতে পারে**, যা **বড় পরিমাণ ডাটা পরিচালনার জন্য আরও কার্যকর**।

একইভাবে, `useReducer()` **স্টেট লজিককে সুগঠিতভাবে পরিচালনা করে**, নিশ্চিত করে যে আপডেটগুলো **পূর্বাভাসযোগ্য ও কেন্দ্রীয়ভাবে নিয়ন্ত্রিত**।

### 📝 উদাহরণ ১: `useReducer()` দিয়ে একটি সাধারণ কাউন্টার

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

**💡 ব্যাখ্যা:**

- **স্টেট একটি অবজেক্ট (`{ count: 0 }`)**, যা **আরও সংগঠিত আপডেটের সুযোগ দেয়**।
- **`dispatch({ type: "increment" })` একটি অ্যাকশন পাঠায়**, এবং **`reducer` স্টেট পরিবর্তনের সিদ্ধান্ত নেয়**।
- এই পদ্ধতিটি **অপ্রয়োজনীয় রি-রেন্ডার প্রতিরোধ করে**, কারণ **শুধুমাত্র নির্দিষ্ট স্টেট পরিবর্তন ট্রিগার হয়**।

**📌 সাধারণ ভুল:** **`useReducer()` সহজ ক্ষেত্রে ব্যবহার করা যেখানে `useState()` যথেষ্ট**, এতে **কোড অপ্রয়োজনীয়ভাবে জটিল হয়ে যায়**।

### 📝 উদাহরণ 2: `useReducer()` ব্যবহার করে টুডো লিস্ট পরিচালনা করা

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

**💡 ব্যাখ্যা:**

- **একটি অ্যাকশন (`add`) পাঠালে নতুন টুডো যুক্ত হয়**।
- **`remove` অ্যাকশনে নির্দিষ্ট টুডো অপসারণ হয় পুরো অ্যারের পরিবর্তন না করে**।
- `useState()` ব্যবহার করে **প্রতিবার অ্যারের নতুন কপি তৈরি না করে**, `useReducer()` **আরও দক্ষভাবে পরিচালনা করে।**

**📌 সাধারণ ভুল:** নতুন স্টেট রিটার্ন না করে স্টেট সরাসরি পরিবর্তন করা (যেমন, `state.push(todo)`), যা **বাগ সৃষ্টি করতে পারে**।

### 📌 বাস্তব জীবনে কোথায় ব্যবহার হয়

- **বড় অ্যাপে গ্লোবাল স্টেট পরিচালনা করতে**
- **একাধিক ইউজার ইন্টারঅ্যাকশন পরিচালনা করতে যেখানে একাধিক আপডেট প্রয়োজন**
- **Redux-এর মতো প্যাটার্ন React-এ ব্যবহার করতে, এক্সট্রা লাইব্রেরি ছাড়াই**

<br>

## ৮. 🔄 কাস্টম Hooks তৈরি করা – React কোড পুনঃব্যবহারযোগ্য ও স্কেলেবল করা

**🛠️ ভূমিকা**

React-এর বিল্ট-ইন হুক (`useState()`, `useEffect()` ইত্যাদি) **কম্পোনেন্ট লজিক সহজতর করতে সাহায্য করে**, কিন্তু যদি **একাধিক কম্পোনেন্টে একই কার্যকারিতা প্রয়োজন হয়**, তখন কী করবো?

**কাস্টম Hooks** ডেভেলপারদের **কম্পোনেন্ট থেকে সাধারণ লজিক আলাদা করে, বারবার ব্যবহারের জন্য পুনঃব্যবহারযোগ্য করতে** সাহায্য করে, যা **কোডকে আরও পরিষ্কার, স্কেলেবল ও রক্ষণাবেক্ষণযোগ্য করে**।

একাধিক কম্পোনেন্টে **একই লজিক বারবার লেখার পরিবর্তে, একটি কাস্টম Hook তৈরি করে** সেটিকে **বারবার ব্যবহার করা যায়**, যা **প্রসারযোগ্যতা ও আপডেট সহজ করে**।

### 💡 সহজ উদাহরণ: আলাদা অ্যাডাপ্টার বানানোর বদলে একটি ইউনিভার্সাল ফোন চার্জার তৈরি করা

প্রতিটি ডিভাইসের জন্য **আলাদা অ্যাডাপ্টার তৈরি করার পরিবর্তে**, একটি **ইউনিভার্সাল চার্জার** বানালে **সব ব্র্যান্ডের জন্য চার্জিং সহজ হয়ে যায়**।

একইভাবে, **কাস্টম Hooks সাধারণ লজিককে কেন্দ্রীভূত করে**, যাতে **একাধিক কম্পোনেন্ট দক্ষতার সঙ্গে ব্যবহার করতে পারে**।

### 📝 উদাহরণ ১: `useFetch()` কাস্টম Hook তৈরি করা API কলের জন্য

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

// কাস্টম Hook ব্যবহার করা
const Component = () => {
  const { data, loading } = useFetch("https://api.example.com/data");
  return <div>{loading ? "লোড হচ্ছে..." : JSON.stringify(data)}</div>;
};
```

**💡 ব্যাখ্যা:**

- `useFetch(url)` **API কল পরিচালনা করে**, যা **একাধিক কম্পোনেন্টের জন্য পুনঃব্যবহারযোগ্য হয়**।
- **একই লজিক বারবার লেখার প্রয়োজন নেই**, যা **রক্ষণাবেক্ষণ সহজ করে**।
- `useFetch()` ব্যবহার করলে **স্বয়ংক্রিয়ভাবে লোডিং স্টেট ও ডাটা পাওয়া যায়**, যা **কোডকে আরও কার্যকর করে**।

**📌 সাধারণ ভুল:** `useEffect()`**-এ ডিপেন্ডেন্সি অ্যারে (`[url]`) না দেওয়া**, যার ফলে **অনিয়ন্ত্রিত API কল হতে পারে।**

### 📝 উদাহরণ ২: useDebounce() কাস্টম Hook তৈরি করে ইনপুট পারফরম্যান্স উন্নত করা

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

// কাস্টম Hook ব্যবহার করা
const SearchBar = () => {
  const [query, setQuery] = useState("");
  const debouncedQuery = useDebounce(query, 500);

  useEffect(() => {
    console.log("সার্চ করা হচ্ছে:", debouncedQuery);
  }, [debouncedQuery]);

  return <input onChange={(e) => setQuery(e.target.value)} placeholder="সার্চ করুন..." />;
};
```

**💡 ব্যাখ্যা:**

- `useDebounce()` **স্টেট আপডেট বিলম্বিত করে**, যাতে **প্রতিটি কী প্রেসে API কল না হয়**।
- **সার্চ বার, অটো-সাজেশন, ও রিয়েল-টাইম ফিল্টারিং-এ পারফরম্যান্স উন্নত করতে কার্যকর।**

### 📌 বাস্তব জীবনে কোথায় ব্যবহার হয়

- **API ডাটা দক্ষতার সাথে ফেচ করা**
- **Authentication স্টেট পরিচালনা করা**
- **পুনঃব্যবহারযোগ্য UI বিহেভিয়র পরিচালনা করা** (অ্যানিমেশন, ফর্ম ভ্যালিডেশন, ডিবাউন্স ফাংশন ইত্যাদি)

<br>

## ৯. 📤 React Portals মাস্টার করা – মূল DOM-এর বাইরে কম্পোনেন্ট রেন্ডার করা

**🚪 ভূমিকা**

React সাধারণত **প্রাথমিক DOM ট্রির ভেতরে কম্পোনেন্ট রেন্ডার করে**, কিন্তু অনেক সময় **প্রধান স্ট্রাকচারের বাইরে UI উপাদান রেন্ডার করতে হয়—যেমন**:

- **মডাল**, যা overflow স্টাইল দ্বারা প্রভাবিত হতে পারে

- **টুলটিপ**, যা সঠিকভাবে absolute পজিশনিং প্রয়োজন

- **নোটিফিকেশন**, যা গ্লোবালি দেখাতে হবে

**React-এর state ও lifecycle ধরে রেখে** React **Portals কম্পোনেন্টকে মূল DOM ট্রির বাইরে রেন্ডার করতে দেয়**।

### 💡 সহজ উদাহরণ: থিয়েটারের VIP প্রবেশপথ

ধরো **তুমি থিয়েটারে যাচ্ছো**, কিন্তু **প্রধান গেটের বদলে VIP প্রবেশপথ ব্যবহার করছো**।

একইভাবে, **React Portals কম্পোনেন্টকে মূল স্ট্রাকচার ছাড়াই রেন্ডার করতে দেয়**, কিন্তু **React state ও ইভেন্ট পরিচালনা অপরিবর্তিত থাকে**।

### 📝 উদাহরণ ১: `createPortal()` ব্যবহার করে মডাল তৈরি

```jsx
import ReactDOM from "react-dom";

const modalRoot = document.getElementById("modal-root");

const Modal = ({ children }) => {
  return ReactDOM.createPortal(children, modalRoot);
};
```

**💡 ব্যাখ্যা:**

- সাধারণত **React কম্পোনেন্ট মূল DOM ট্রির মধ্যে রেন্ডার হয়**, কিন্তু **এটি `modalRoot`-এর মধ্যে রেন্ডার হচ্ছে**।

- **মডাল, ওভারলে, ও ডায়নামিক UI উপাদানের জন্য আদর্শ**।

**📌 সাধারণ ভুল:** Portals `modalRoot`**-এর মতো একটি নির্দিষ্ট কন্টেইনার ছাড়া ব্যবহার করা**, যা **অপ্রত্যাশিত স্টাইলিং সমস্যা তৈরি করতে পারে**।

### 📝 উদাহরণ ২: ক্লিক করে মডাল খোলার ব্যবস্থা

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

**💡 ব্যাখ্যা:**

- `"Open Modal"` বোতামে ক্লিক করলে **মডালটি `modalRoot`-এর মধ্যে রেন্ডার হয়**, যাতে **overflow বা z-index সমস্যা এড়ানো যায়**।

- `"Close"` বোতামে ক্লিক করলে **মডাল বন্ধ হয়**, যা **React state দিয়ে নিয়ন্ত্রণ করা যায়**।

### 📌 বাস্তব জীবনে কোথায় ব্যবহার হয়

- **মেইন UI স্ট্রাকচার পরিবর্তন না করে মডাল তৈরি করতে**
- **টুলটিপ রেন্ডার করতে যেখানে সঠিক পজিশন প্রয়োজন**
- **মূল কম্পোনেন্ট ট্রির বাইরে নোটিফিকেশন দেখাতে**

<br>

## ১০. ⚡ Concurrent Rendering আনলক করা – React অ্যাপ আরও দ্রুত ও স্মুথ করা

**🚀 ভূমিকা**

React সাধারণত **আপডেটগুলো সিনক্রোনাসভাবে প্রক্রিয়া করে**, যার ফলে এটি **অন্য কাজগুলো ব্লক করে** যতক্ষণ না রেন্ডারিং সম্পন্ন হয়। জটিল অ্যাপ্লিকেশনগুলিতে এটি **UI ফ্রিজ, ল্যাগ, ও ব্যবহারকারীর খারাপ অভিজ্ঞতা তৈরি করতে পারে**, বিশেষত যখন **বড় তালিকা, অ্যানিমেশন, বা ব্যয়বহুল গণনা** সম্পন্ন হয়।

React **Concurrent Rendering (React 18)** এমন কৌশল উপস্থাপন করেছে যা **জরুরি UI কাজকে অগ্রাধিকার দেয়, কম গুরুত্বপূর্ণ আপডেটগুলো বিলম্বিত করে**, ফলে **রেসপনসিভনেস ও দক্ষতা উন্নত হয়**।

### 💡 সহজ উদাহরণ: খাবারের অপেক্ষায় থাকলেও কফি আগে পরিবেশন করা

ধরো **একটি রেস্টুরেন্টে তুমি খাবার অর্ডার করেছো**। সম্পূর্ণ খাবার তৈরি হওয়ার জন্য অপেক্ষা না করে, রেস্তোরাঁ **আগে দ্রুত কফি পরিবেশন করে**, যেন তুমি **অপেক্ষার সময় কিছু পান করতে পারো**।

একইভাবে, **Concurrent Rendering নিশ্চিত করে যে উচ্চ-অগ্রাধিকার আপডেট (যেমন ব্যবহারকারীর ইন্টারঅ্যাকশন) তাৎক্ষণিকভাবে পরিচালিত হয়**, আর **নিম্ন-অগ্রাধিকার আপডেট (যেমন ডাটা ফেচিং) পরে হয়**।

### 📝 উদাহরণ ১: `startTransition()` ব্যবহার করে UI আপডেটকে অগ্রাধিকার দেওয়া

```jsx
import { useState, startTransition } from "react";

const SearchComponent = () => {
  const [query, setQuery] = useState("");
  const [results, setResults] = useState([]);

  const handleSearch = (input) => {
    setQuery(input); // তাৎক্ষণিক UI আপডেট

    startTransition(() => {
      setResults(["Apple", "Banana", "Cherry"].filter((item) => item.toLowerCase().includes(input.toLowerCase())));
    });
  };

  return (
    <div>
      <input onChange={(e) => handleSearch(e.target.value)} placeholder="সার্চ করুন..." />
      <ul>
        {results.map((r, i) => (
          <li key={i}>{r}</li>
        ))}
      </ul>
    </div>
  );
};
```

**💡 ব্যাখ্যা:**

- `setQuery(input)` **তাৎক্ষণিকভাবে সার্চ ফিল্ড আপডেট করে**, যাতে ব্যবহারকারী দ্**রুত ইনপুট দেখতে পারেন**।
- `startTransition()` **ব্যবহার করে React ফিল্টারিং বিলম্বিত করে**, যাতে **টাইপিংয়ের সময় ল্যাগ না হয়**।
- **বড় ডাটাসেটে পারফরম্যান্স উন্নত করে**, নিশ্চিত করে **দ্রুত UI রেসপন্স**।

**📌 সাধারণ ভুল:** `startTransition()` **জরুরি আপডেটের (যেমন বাটন ক্লিক বা ফর্ম সাবমিট) জন্য ব্যবহার করা**, যা **অনাকাঙ্ক্ষিত বিলম্ব তৈরি করতে পারে**।

### 📝 উদাহরণ ২: `useTransition()` ব্যবহার করে বড় তালিকার UI ফ্রিজ প্রতিরোধ

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
      <input onChange={(e) => handleFilter(e.target.value)} placeholder="তালিকা ফিল্টার করুন..." />
      {isPending && <p>তালিকা আপডেট হচ্ছে...</p>}
      <ul>
        {filteredItems.map((item, index) => (
          <li key={index}>{item}</li>
        ))}
      </ul>
    </div>
  );
};
```

**💡 ব্যাখ্যা:**

- `useTransition()` React-কে **উচ্চ-অগ্রাধিকার কাজ (যেমন ইনপুট আপডেট) আগে করতে দেয়**, তারপরে **ব্যয়বহুল ফিল্টারিং পরিচালনা করে**।
- **UI ব্লক না করে** তালিকা আপডেট করে, ফলে **জটিল ডাটাসেটে পারফরম্যান্স উন্নত হয়**।
- **বড় তালিকায় পারফরম্যান্স সমস্যার সমাধান করে**, নিশ্চিত করে **স্মুথ UI এক্সপেরিয়েন্স**।

### 📌 বাস্তব জীবনে কোথায় ব্যবহার হয়

- **সার্চ ইনপুট পরিচালনা করতে যেখানে UI ফ্রিজ হওয়া উচিত নয়**
- **বড় তালিকায় ল্যাগ প্রতিরোধ করতে**
- **অ্যানিমেশন ও ডায়নামিক রেন্ডারিংয়ের সময় ব্যবহারকারীর অভিজ্ঞতা উন্নত করতে**

<br>
