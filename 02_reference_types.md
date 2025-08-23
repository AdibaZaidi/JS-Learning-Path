# Reference Types in JavaScript

Unlike primitives, reference types are stored as a **reference (pointer) in memory**.  

---

## Types of Reference Data Types
1. Objects  
2. Arrays  
3. Functions  

---

## 1. Objects  
Objects are collections of key-value pairs.  

**Example:**  

```js
let person = {
  name: "Adiba",
  age: 23
};

console.log(person.name); // Adiba
console.log(person.age);  // 23
````

---

## 2. Arrays

Arrays are special objects used to store ordered collections.

**Example:**

```js
let numbers = [10, 20, 30];

console.log(numbers[0]);      // 10
console.log(numbers.length);  // 3
```

---

## 3. Functions

Functions are first-class objects in JavaScript (they can be assigned to variables, passed as arguments, and returned).

**Example:**

```js
function greet(name) {
  return "Hello " + name;
}

console.log(greet("Adiba")); // Hello Adiba
```

---

## Value Type vs Reference Type Behavior

**Example:**

```js
// Primitive (Value Type)
let a = 10;
let b = a;
b = 20;

console.log(a); // 10
console.log(b); // 20

// Reference Type
let obj1 = { value: 10 };
let obj2 = obj1;
obj2.value = 20;

console.log(obj1.value); // 20 (changed because both point to same memory)
console.log(obj2.value); // 20
```
