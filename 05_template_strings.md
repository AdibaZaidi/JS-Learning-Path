# Template Strings (Template Literals)  

Template strings (introduced in ES6) use **backticks (``)** instead of quotes.  
They allow:  
1. **String Interpolation** – embedding variables.  
2. **Multi-line Strings**.  

---

## Example: String Interpolation
```js
let name = "Adiba";
let age = 23;

let intro = `My name is ${name} and I am ${age} years old.`;
console.log(intro);
// My name is Abc and I am 23 years old.
```

## Example: Multi-line String
```js
let poem = `Roses are red,
Violets are blue,
JavaScript is awesome,
And so are you.`;

console.log(poem);
