For Loop in JavaScript
The for loop is one of the most commonly used loops in JavaScript.
It allows you to run a block of code multiple times with a counter variable.

1. Syntax
```
for (initialization; condition; increment/decrement) {
    // code to run
}
```

initialization → sets a starting value (e.g., let i = 0)
condition → loop continues while this is true
increment/decrement → updates the counter (i++, i--, etc.)

# 2. Basic Example
```
for (let i = 1; i <= 5; i++) {
    console.log("Count: " + i);
}
Output:
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
```

# 3. Looping Through an Array
```
const fruits = ["Apple", "Banana", "Mango", "Orange"];

for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}
Output:
Apple
Banana
Mango
Orange
```

# 4. Reverse Loop
```
for (let i = 5; i >= 1; i--) {
    console.log(i);
}
Output:
5
4
3
2
1
```

# 5. Skipping with continue
```
for (let i = 1; i <= 5; i++) {
    if (i === 3) continue; // skip 3
    console.log(i);
}
Output:
1
2
4
5
```

# 6. Stopping with break
```
for (let i = 1; i <= 5; i++) {
    if (i === 4) break; // stop at 4
    console.log(i);
}
Output:
1
2
3
```

# 7. Nested For Loops
```
for (let i = 1; i <= 3; i++) {
    for (let j = 1; j <= 2; j++) {
        console.log(`i = ${i}, j = ${j}`);
    }
}
Output:
i = 1, j = 1
i = 1, j = 2
i = 2, j = 1
i = 2, j = 2
i = 3, j = 1
i = 3, j = 2
```
✅ Summary
for loop = controlled repetition
Useful when you know how many times to run
Can loop forward, backward, skip (continue), or stop (break)
