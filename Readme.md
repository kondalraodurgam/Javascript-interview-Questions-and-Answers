
# 📘 Frontend Notes

## 📙 JavaScript

### 1. What is Scope in JavaScript

Scope refers to the accessibility of variables, functions, and objects in certain parts of your code during runtime.

There are **3 types of scope**:
- **Global Scope** – Accessible from anywhere.
- **Function Scope** – Accessible only within a function.
- **Block Scope** – Accessible only within a block (e.g., `if`, `for`).

```javascript
function test() {
  if (true) {
    var a = 10;
    let b = 20;
  }
  console.log(a); // 10
  console.log(b); // ReferenceError
}
test();
```

---

### 2. What is Hoisting in JavaScript

Hoisting is the behavior where JavaScript moves variable and function declarations to the top of their scope during the compilation phase.

```javascript
x = 10;
console.log(x); // 10
var x;
```

---

### 3. Difference between `var`, `let`, and `const`

- `var`: Function-scoped
- `let`: Block-scoped
- `const`: Block-scoped, but value can't be reassigned

```javascript
function example() {
  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;
  }
  console.log(a); // 1
  console.log(b); // ReferenceError
  console.log(c); // ReferenceError
}
```

---

### 4. Primitive vs Non-Primitive Data Types

- **Primitive**: `String`, `Number`, `Boolean`, `Null`, `Undefined`, `Symbol`, `BigInt` → Immutable  
- **Non-Primitive**: `Object`, `Array`, `Function`, `Date`, `RegExp` → Mutable

```javascript
let str = "hello"; // Primitive
let obj = { name: "John" }; // Non-Primitive
```

---

### 5. What is a Callback Function?

A callback is a function passed into another function as an argument and executed after an operation is completed.

```javascript
function greet(name) {
  console.log("Hello " + name);
}
function askUser(callback) {
  let name = prompt("Enter your name");
  callback(name);
}
askUser(greet);
```

---

### 6. What are Closures?

A closure is an inner function that has access to the outer function’s variables.

```javascript
function Welcome(name) {
  return function (message) {
    console.log(message + " " + name);
  };
}
const greet = Welcome("John");
greet("Welcome"); // Welcome John
greet("Hello Mr."); // Hello Mr. John
```

---

### 7. What is a Promise?

A Promise represents the eventual completion (or failure) of an async operation.

- States: `pending`, `fulfilled`, `rejected`

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("I'm a Promise!");
  }, 2000);
});

promise.then(console.log);
```

---

### 8. `==` vs `===`

- `==`: Loose equality (type coercion)
- `===`: Strict equality (no coercion)

```javascript
1 == "1";  // true
1 === "1"; // false
```

---

### 9. What is the Event Loop?

The Event Loop handles asynchronous callbacks and ensures non-blocking execution in JavaScript.

```javascript
console.log("Start");
setTimeout(() => console.log("Async Task"), 0);
console.log("End");
```

---

### 10. Synchronous vs Asynchronous

- **Synchronous**: Executes line-by-line  
- **Asynchronous**: Executes independently using callbacks, promises, or async/await

---

## ⚛️ React

### 1. Lifecycle Methods

For **class components**:
- `componentDidMount`
- `componentDidUpdate`
- `componentWillUnmount`

For **functional components**, use `useEffect` as an equivalent.

---

### 2. State vs Props

- **Props**: Passed from parent to child; read-only
- **State**: Local to a component; mutable

---

### 3. Rules of Hooks

- Only call Hooks at the top level
- Only inside functional components
- Don't call Hooks inside loops, conditions, or nested functions

```javascript
const [count, setCount] = useState(0);

useEffect(() => {
  console.log("Effect runs");
}, [count]);
```

---

### 4. Context Hook

Allows global state sharing without prop drilling.

---

### 5. useReducer Hook

Useful for complex state logic.

```javascript
const [state, dispatch] = useReducer(reducer, initialState);
```

---

## 🧠 Redux

### Core Concepts

- **Store**: Central state container  
- **Action**: Describes what happened  
- **Reducer**: Describes how the state changes  

---

### Flux vs Redux

| Feature       | Flux       | Redux                |
|---------------|------------|----------------------|
| State         | Mutable    | Immutable            |
| Stores        | Multiple   | Single               |
| Dispatcher    | Required   | Not used             |
| Data Flow     | Disconnected | Hierarchical reducers |

---

## 🎨 CSS

### 1. CSS Box Model

- **Content**: Actual content (text/images)  
- **Padding**: Space around content (inside border)  
- **Border**: Surrounds padding  
- **Margin**: Space outside border  

---

## 🌐 HTML

```html
<article><aside><details><figcaption><figure>
<footer><form><header><main><mark>
<nav><section><summary><time>
```

---

## 🅰️ Angular

### Promises vs Observables

| Feature     | Promises | Observables                  |
|-------------|----------|------------------------------|
| Values      | Single   | Multiple                     |
| Lazy        | No       | Yes                          |
| Cancellable | No       | Yes                          |
| Operators   | None     | Many (map, filter, etc.)     |

---
