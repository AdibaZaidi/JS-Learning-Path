# Arrays in JavaScript

Arrays in JavaScript are used to store multiple values in a single variable. Each value has an index (starting from 0).

---

## Array of Objects

An **array of objects** means you store multiple objects inside an array. This is very useful when working with structured data, like lists of users, products, or books.

### Example: Students Data
```js
let students = [
    { id: 1, name: "Ad", age: 23 },
    { id: 2, name: "Ka", age: 25 },
    { id: 3, name: "Sara", age: 22 }
];

// Accessing values
console.log(students[0].name);  // "Ad"
console.log(students[1].age);   // 25

// Updating a value
students[2].age = 23;
console.log(students[2]); // { id: 3, name: "Sara", age: 23 }
Example: Products List
let products = [
    { id: 101, name: "Laptop", price: 50000 },
    { id: 102, name: "Phone", price: 20000 },
    { id: 103, name: "Tablet", price: 15000 }
];

// Loop through array of objects
products.forEach(product => {
    console.log(`${product.name} costs ₹${product.price}`);
});

// Output:
// Laptop costs ₹50000
// Phone costs ₹20000
// Tablet costs ₹15000
```

## Finding an Object in Array
```
let users = [
    { id: 1, username: "Al" },
    { id: 2, username: "Fatima" },
    { id: 3, username: "Im" }
];

let user = users.find(u => u.id === 2);
console.log(user); // { id: 2, username: "Fatima" }
```

## Filtering Objects
```
let employees = [
    { name: "John", dept: "IT" },
    { name: "Sara", dept: "HR" },
    { name: "Ka", dept: "IT" }
];

let itEmployees = employees.filter(emp => emp.dept === "IT");
console.log(itEmployees);
// [
//   { name: "John", dept: "IT" },
//   { name: "Ka", dept: "IT" }
// ]
```
✅ Arrays of objects are widely used in real projects — such as storing records fetched from APIs, databases, or form inputs.

---

## Objects in JavaScript

Objects are collections of key–value pairs. They help store related data together.

---

## Relation Between Arrays and Objects

- Arrays can contain objects.
- Objects can also have arrays as property values.

---

### Example: Object Containing Array
```js
let person = {
    name: "Adiba",
    hobbies: ["Reading", "Gaming", "Traveling"]
};

console.log(person.hobbies[1]); // "Gaming"
Example: Array of Objects
let cars = [
    { brand: "Toyota", model: "Corolla", year: 2020 },
    { brand: "Honda", model: "Civic", year: 2022 },
    { brand: "Tesla", model: "Model 3", year: 2023 }
];

console.log(cars[0].brand); // "Toyota"
console.log(cars[2].model); // "Model 3"
Example: Nested Structure
let library = [
    {
        title: "The Alchemist",
        author: "Paulo Coelho",
        genres: ["Fiction", "Adventure"]
    },
    {
        title: "Atomic Habits",
        author: "James Clear",
        genres: ["Self-help", "Productivity"]
    }
];

console.log(library[1].genres[0]); // "Self-help"
```
✅ Combining arrays and objects allows you to represent complex, real-world data structures effectively.
