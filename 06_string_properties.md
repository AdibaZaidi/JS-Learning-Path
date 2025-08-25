# String Properties in JavaScript  

Strings in JavaScript are **primitive values**, but they behave like objects because they have built-in properties and methods.  

---

## `.length` Property  
Gives the total number of characters.  

```js
let name = "Adiba";
console.log(name.length); // 5
```

## Common String Methods
**.toUpperCase() and .toLowerCase()**
```js
let str = "JavaScript";
console.log(str.toUpperCase()); // JAVASCRIPT
console.log(str.toLowerCase()); // javascript
```
**.charAt(index)**
```js
let word = "Hello";
console.log(word.charAt(0)); // H
```
**.includes()**
```js
let msg = "Learning JS is fun";
console.log(msg.includes("JS")); // true
console.log(msg.includes("Python")); // false
```
**.slice(start, end)**
```js
let text = "AdZain";
console.log(text.slice(0, 5)); // AdZai
```
