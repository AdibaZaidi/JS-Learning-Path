# JavaScript is a Multi-Paradigm Language  

JavaScript supports different programming **paradigms (styles of programming)**:  

1. **Procedural Programming** – Writing step-by-step instructions.  
2. **Object-Oriented Programming (OOP)** – Organizing code into objects.  
3. **Functional Programming (FP)** – Using functions as first-class citizens.  

---

## Example: Procedural Style
```js
let numbers = [1, 2, 3];
for (let i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
}
````

## Example: Object-Oriented Style
```js
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    console.log("Hello, my name is " + this.name);
  }
}

let p = new Person("Adiba");
p.greet();
````

## Example: Functional Style
```js
let numbers = [1, 2, 3];
numbers.forEach(n => console.log(n));
````

👉 JavaScript is flexible because it supports multiple paradigms in one language.
