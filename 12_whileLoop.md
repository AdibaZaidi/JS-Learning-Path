# While Loop in JavaScript
The while loop is used when you want to repeat a block of code as long as a condition is true.
Unlike the for loop, you don’t know in advance how many times the loop will run.

# 1. Syntax
```
while (condition) {
    // code to run
}
```
condition → checked before each iteration.
If true, code inside the loop runs.
If false, the loop stops.

# 2. Basic Example
```
let i = 1;

while (i <= 5) {
    console.log("Count: " + i);
    i++;
}
Output:
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
```

# 3. Infinite Loop (⚠️ Be Careful!)
If you forget to update the condition, the loop will run forever:
```
let x = 1;

while (x > 0) {
    console.log("This will run forever!");
}
```
👉 Always make sure the condition eventually becomes false.

# 4. Using break to Stop
```
let i = 1;

while (true) {
    console.log(i);
    if (i === 3) break; // stop at 3
    i++;
}
Output:
1
2
3
```

# 5. Using continue to Skip
```
let i = 0;

while (i < 5) {
    i++;
    if (i === 3) continue; // skip 3
    console.log(i);
}
Output:
1
2
4
5
```

# 6. Example: Sum of Numbers
```
let n = 5;
let sum = 0;
let i = 1;

while (i <= n) {
    sum += i;
    i++;
}

console.log("Sum = " + sum);
Output:
Sum = 15
```
✅ Summary
while checks the condition before running the loop.
Good when you don’t know the number of iterations in advance.
Use break and continue to control flow.
