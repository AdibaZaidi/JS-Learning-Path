# JavaScript Objects — A Practical Guide

Objects store data as **key–value** pairs. Keys are strings (or Symbols); values can be any type.

---

## Creating Objects

```js
const person = { name: "Ad", age: 23 };  // literal
const empty  = new Object();                 // rarely needed
empty.city = "Mumbai";

// Computed property names
const key = "fav-color";
const obj = { [key]: "teal" };
```

## Accessing Properties
```
const user = { name: "Ka", score: 42 };
console.log(user.name);          // dot
console.log(user["score"]);      // bracket (dynamic keys)
const prop = "name";
console.log(user[prop]);         // "Ka"
```

## Optional Chaining & Defaults
```
const data = { a: { b: { c: 5 } } };
console.log(data?.a?.b?.c ?? 0); // 5
console.log(data?.x?.y ?? "none"); // "none"
Add, Update, Delete
const profile = { name: "Am" };
profile.age = 24;               // add/update
delete profile.name;            // delete
console.log("name" in profile); // false
```
Prefer setting to undefined only when you need the key to exist but be empty;
delete changes shape and can affect performance in hot code.

## Enumerating Properties
```
const p = { a: 1, b: 2 };

Object.keys(p);                 // ["a","b"]
Object.values(p);               // [1,2]
Object.entries(p);              // [["a",1],["b",2]]

for (const [k, v] of Object.entries(p)) {
  console.log(k, v);
}

// for...in includes inherited keys; filter with hasOwn
for (const k in p) {
  if (Object.prototype.hasOwnProperty.call(p, k)) {
    console.log(k);
  }
}
```
Create from entries:
```
const pairs = [["x", 1], ["y", 2]];
const rebuilt = Object.fromEntries(pairs);   // { x:1, y:2 }
```

## Copying & Merging (Shallow)
```
const a = { x: 1, nested: { y: 2 } };

const copy1 = { ...a };                 // spread (shallow)
const copy2 = Object.assign({}, a);     // shallow

copy1.nested.y = 99;
console.log(a.nested.y);                // 99 (same reference)

// Merge
const defaults = { theme: "light", page: 1 };
const overrides = { page: 3 };
const merged = { ...defaults, ...overrides }; // { theme:"light", page:3 }
```

## Deep Copy
```
const deep = structuredClone(a); // modern & safe for most built-ins
// JSON trick (loses functions, Date, Map/Set, undefined, Symbols)
const deepJson = JSON.parse(JSON.stringify(a));
```

## Immutability Helpers
Update nested without mutation:
```
const state = { user: { name: "Noor", address: { city: "Delhi" } } };

const next = {
  ...state,
  user: {
    ...state.user,
    address: {
      ...state.user.address,
      city: "Mumbai"
    }
  }
};

```
