# JavaScript Arrays — A Practical Guide

Arrays store ordered lists of values. They can hold numbers, strings, objects, functions—even other arrays.

---

## Quick Start

```js
const fruits = ["apple", "banana", "mango"];
const mixed = [1, "two", { three: 3 }, [4]];
console.log(fruits[0]);              // "apple"
console.log(fruits.length);          // 3
Creating Arrays
const a = [];                        // empty
const b = [1, 2, 3];                 // literal
const c = Array(3);                  // length 3, holes
const d = Array.of(1, 2, 3);         // [1,2,3]
const e = Array.from("hello");       // ["h","e","l","l","o"]
✅ Check type: Array.isArray(x).
```

## Reading, Writing, and Length
```
const nums = [10, 20, 30];
nums[1] = 99;                        // mutate index 1
nums[10] = 5;                        // creates holes between 3..9
console.log(nums.length);            // 11
⚠️ length is writable: nums.length = 2 truncates the array.
```

## Adding/Removing Elements
**Fast at the end**
```
const arr = [1,2,3];
arr.push(4);        // [1,2,3,4]
arr.pop();          // [1,2,3]
```
**Slower at the start (shifts indices)**
```
arr.unshift(0);     // [0,1,2,3]
arr.shift();        // [1,2,3]
```
**Slice vs Splice**
slice(start, end?): non-mutating copy.
splice(start, deleteCount, ...items): mutates (remove/insert).
```
const x = [1,2,3,4,5];
console.log(x.slice(1, 4));   // [2,3,4]  (x unchanged)

x.splice(2, 2, "A", "B");     // remove 2 at index 2, insert A,B
console.log(x);               // [1,2,"A","B",5]
```
**Concatenate / Copy**
```
const a1 = [1,2], a2 = [3,4];
const cat1 = a1.concat(a2);   // [1,2,3,4]
const cat2 = [...a1, ...a2];  // [1,2,3,4]
const copy = x.slice();       // shallow copy
```
**Iteration Patterns**
```
const arr = [2,4,6];

// Classic for
for (let i = 0; i < arr.length; i++) console.log(arr[i]);

// for...of (values)
for (const v of arr) console.log(v);

// forEach (callback; cannot break)
arr.forEach((v, i) => console.log(i, v));
```
**Transform, Search, and Test**
```
const nums = [1,2,3,4,5];

const squared = nums.map(n => n * n);            // [1,4,9,16,25]
const evens   = nums.filter(n => n % 2 === 0);   // [2,4]
const sum     = nums.reduce((a, n) => a + n, 0); // 15
const anyBig  = nums.some(n => n > 3);           // true
const allBig  = nums.every(n => n > 0);          // true

const firstEven     = nums.find(n => n % 2 === 0);      // 2
const firstEvenIdx  = nums.findIndex(n => n % 2 === 0); // 1

nums.includes(3);                               // true
nums.indexOf(3);                                // 2
[NaN].includes(NaN);                            // true (SameValueZero)
[NaN].indexOf(NaN);                             // -1 (=== check)
```
**Sorting & Reversing**
```
const vals = [10, 1, 20, 3];
vals.sort();                 // ["1","10","20","3"]  (string compare!)

vals.sort((a,b) => a - b);   // [1,3,10,20] numeric
vals.reverse();              // mutates

// Immutable ES2023 variants (do not mutate):
const sorted = vals.toSorted((a,b) => a - b);
const rev    = vals.toReversed();
```
**Flattening**
```
const nested = [1, [2, [3, 4]], 5];
nested.flat(1);              // [1,2,[3,4],5]
nested.flat(2);              // [1,2,3,4,5]

const words = ["hi", "there"];
words.flatMap(w => w.split("")); // ["h","i","t","h","e","r","e"]
```
**Destructuring, Rest & Spread**
```
const data = [1,2,3,4];
const [first, second, ...rest] = data;
console.log(first, second, rest);  // 1 2 [3,4]

const more = [...data, 5, 6];      // [1,2,3,4,5,6]
```
**Copying: Shallow vs Deep**
```
const original = [{ id: 1 }, { id: 2 }];

// Shallow copy (inner objects shared!)
const shallow = original.slice();
shallow[0].id = 99;
console.log(original[0].id);       // 99 (same reference)

// Deep copy (modern)
const deep = structuredClone(original);
deep[0].id = 7;
console.log(original[0].id);       // 99, unaffected

// JSON hack (loses functions/undefined/Date etc.)
const deep2 = JSON.parse(JSON.stringify(original));
Sparse Arrays (Holes)
const s = [];
s[3] = "x";                 // holes at 0,1,2
console.log(s.length);      // 4
console.log(s.map(x => 1)); // [ <3 empty items>, 1 ]
Prefer avoiding holes—they cause surprising behavior.
```
