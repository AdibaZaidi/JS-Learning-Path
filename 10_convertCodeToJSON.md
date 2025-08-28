## Convert Code to JSON
JSON (JavaScript Object Notation) is a lightweight format for storing and transporting data.
It is widely used in APIs and web applications to exchange data between a server and a client.

## 1. What is JSON?
JSON looks like JavaScript objects, but it is always in string format.
Data is represented in key-value pairs.
Keys must be in double quotes.
**Example JSON:**
```
{
  "name": "Ad",
  "age": 23,
  "skills": ["JavaScript", "Python", "SQL"]
}
```

# 2. Converting Object to JSON (Stringify)
In JavaScript, we use JSON.stringify() to convert an object or array into a JSON string.
```
const user = {
  name: "Ad",
  age: 23,
  skills: ["JavaScript", "Python"]
};

const jsonString = JSON.stringify(user);
console.log(jsonString);
// Output: {"name":"Ad","age":23,"skills":["JavaScript","Python"]}
console.log(typeof jsonString); // string
```

# 3. Converting JSON to Object (Parse)
We use JSON.parse() to convert JSON string back into a JavaScript object.
```
const jsonString = '{"name":"Ad","age":23,"skills":["JavaScript","Python"]}';

const userObject = JSON.parse(jsonString);
console.log(userObject);
// Output: { name: 'Ad', age: 23, skills: [ 'JavaScript', 'Python' ] }
console.log(typeof userObject); // object
```

# 4. Arrays in JSON
Arrays can also be converted to JSON strings and back.
```
const numbers = [1, 2, 3, 4, 5];

// Convert array to JSON
const jsonArray = JSON.stringify(numbers);
console.log(jsonArray); // "[1,2,3,4,5]"

// Convert JSON back to array
const parsedArray = JSON.parse(jsonArray);
console.log(parsedArray); // [1, 2, 3, 4, 5]
5. Nested Objects and Arrays
JSON can represent nested data structures easily.
const company = {
  name: "EcoSmart",
  location: "Mumbai",
  employees: [
    { id: 1, name: "Ad" },
    { id: 2, name: "Ka" }
  ]
};

// Convert to JSON
const companyJSON = JSON.stringify(company);
console.log(companyJSON);

// Parse back to JS object
const companyObj = JSON.parse(companyJSON);
console.log(companyObj.employees[1].name); // Ka
```

# 6. Formatting JSON (Pretty Print)
You can make JSON output more readable by passing extra arguments to JSON.stringify().
```
const user = { name: "Ad", age: 23, skills: ["JS", "Python"] };

const prettyJSON = JSON.stringify(user, null, 4); // 4 spaces indentation
console.log(prettyJSON);

/* Output:
{
    "name": "Ad",
    "age": 23,
    "skills": [
        "JS",
        "Python"
    ]
}
*/
```

# 7. Real-life Example (API Data)
When working with APIs, data is usually received in JSON format.
// Example JSON response from API
```
const apiResponse = '{"status":"success","data":{"id":1,"name":"Ad"}}';

// Convert to JS object
const result = JSON.parse(apiResponse);
console.log(result.data.name); // Ad
```
✅ Summary
JSON.stringify(obj) → Convert object/array → JSON string
JSON.parse(jsonString) → Convert JSON string → JS object/array
JSON is used for data storage and API communication
