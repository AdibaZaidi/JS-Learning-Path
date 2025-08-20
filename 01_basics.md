# JavaScript Basics

## 1. JavaScript is a Single-Threaded Language
- **Single threaded** means JavaScript executes one command at a time in a single call stack.
- It cannot run multiple tasks simultaneously (like multi-threaded languages).
- However, with the help of the **Event Loop**, **Web APIs**, and **Callback Queue**, JavaScript achieves **asynchronous behavior**.

**Example:**
```js
console.log("Start");

setTimeout(() => {
  console.log("Async Task");
}, 1000);

console.log("End");
Output:
Start
End
Async Task
👉 Even though setTimeout was set to run after 1 second, JavaScript doesn’t block the execution. It finishes "Start" → "End" first, then executes the async callback.

**2. JavaScript is a Dynamic Language**
You don’t need to declare types explicitly.
The type of a variable can change at runtime.
Example:
let x = 5;       // number
x = "Hello";     // string
x = true;        // boolean
👉 The same variable x can hold values of different types.

**3. Value Types (Primitives)**
JavaScript has 7 primitive types (value types):
Number
String
Boolean
Null
Undefined
Symbol (ES6)
BigInt (ES11)
Example:
let a = 10;          // Number
let b = "Adiba";     // String
let c = true;        // Boolean
let d = null;        // Null
let e;               // Undefined
let f = Symbol("id") // Symbol
let g = 1234567890123456789012345678901234567890n; // BigInt
