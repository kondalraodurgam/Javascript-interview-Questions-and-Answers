# Frontend Notes

## 📘 JavaScript

### 1. What is Scope in JavaScript
Scope refers to the accessibility of variables, functions, and objects in certain parts of your code during runtime.

There are **3 types of scope**:
- **Global Scope** – Accessible from anywhere.
- **Function Scope** – Accessible only within a function.
- **Block Scope** – Accessible only within a block (e.g., `if`, `for`).

```javascript
// Example of Block vs Function Scope
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
Hoisting is JavaScript's default behavior of moving declarations to the top of the current scope during compilation.

```javascript
x = 10;
console.log(x); // 10
var x;
```

---

### 3. Difference between `var`, `let`, and `const`
- `var`: Function-scoped.
- `let`: Block-scoped.
- `const`: Block-scoped and cannot be reassigned.

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
- **Primitive**: String, Number, Boolean, Null, Undefined, Symbol, BigInt (Immutable)
- **Non-Primitive**: Object, Array, Function, Date, RegExp (Mutable)

```javascript
let str = "hello"; // Primitive
let obj = { name: "John" }; // Non-Primitive
```

---

### 5. What is a Callback Function?
A callback is a function passed into another function as an argument, which is then invoked inside the outer function.

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
A closure is an inner function that has access to variables of its outer function scope even after the outer function has returned.

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
A Promise represents the result of an asynchronous operation.

**States**: Pending → Fulfilled / Rejected

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
- `==`: Compares values with type coercion.
- `===`: Compares values and types strictly.

```javascript
1 == "1";  // true
1 === "1"; // false
```

---

### 9. What is the Event Loop?
Event Loop enables JavaScript to perform non-blocking operations by handling callbacks in the queue.

```javascript
console.log("Start");
setTimeout(() => console.log("Async Task"), 0);
console.log("End");
```

---

### 10. Synchronous vs Asynchronous
- **Synchronous**: Code runs line-by-line.
- **Asynchronous**: Code can run in parallel using callbacks, promises, or async/await.

---

## ⚛️ React

### 1. Lifecycle Methods
**Class Components**:
- `componentDidMount`
- `componentDidUpdate`
- `componentWillUnmount`

**Functional Components**:
Use `useEffect` hook as an equivalent.

---

### 2. State vs Props
- **Props**: Data passed from parent to child, read-only.
- **State**: Local to a component, mutable.

---

### 3. Rules of Hooks
- Only call hooks at the top level.
- Only call inside React functional components.
- Do not call inside loops, conditions, or nested functions.

```javascript
const [count, setCount] = useState(0);

useEffect(() => {
  console.log("Effect runs");
}, [count]);
```

---

### 4. Context Hook
Allows state sharing between components without prop drilling.

---

### 5. useReducer Hook
Used for managing complex state logic.

```javascript
const [state, dispatch] = useReducer(reducer, initialState);
```

---

## 🧠 Redux

### Core Concepts
- **Store**: Centralized state container
- **Action**: Object that describes what happened
- **Reducer**: Pure function to update the state

---

### Flux vs Redux

| Feature       | Flux      | Redux         |
|---------------|-----------|---------------|
| State         | Mutable   | Immutable     |
| Stores        | Multiple  | Single        |
| Dispatcher    | Required  | Not used      |
| Data Flow     | Disconnected | Hierarchical |

---

## 🎨 CSS

### 1. CSS Box Model
- **Content**: Text/images
- **Padding**: Space inside the border
- **Border**: Surrounds padding
- **Margin**: Space outside the border

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

| Feature    | Promises | Observables             |
|------------|----------|--------------------------|
| Values     | Single   | Multiple                 |
| Lazy       | No       | Yes                      |
| Cancellable| No       | Yes                      |
| Operators  | None     | Many (map, filter, etc.) |

---

## 🎯 JavaScript Interview Questions

1. What is the difference between `null` and `undefined`?
2. What is the Temporal Dead Zone in ES6?
3. Explain event delegation.
4. What is a higher-order function?
5. How does `this` work in arrow functions?

---

## ⚛️ React Interview Questions

1. What are the differences between functional and class components?
2. What is React reconciliation?
3. What is the difference between `useEffect` and `useLayoutEffect`?
4. How do you optimize performance in a React application?
5. What are React keys and why are they important?

