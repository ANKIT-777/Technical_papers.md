# Technical - Paper for {JAVASCRIPT}

# Loops in JavaScript

## for loop
```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

## forEach
```javascript
const array = [1, 2, 3];
array.forEach(item => {
  console.log(item);
});
```

## for..in
```javascript
const obj = { a: 1, b: 2, c: 3 };
for (let key in obj) {
  console.log(key, obj[key]);
}
```

## for..of
```javascript
const iterable = [1, 2, 3];
for (let value of iterable) {
  console.log(value);
}
```

## while
```javascript
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
```


## Mutable (Arrays)
```javascript
let mutableArray = [1, 2, 3];
mutableArray.push(4); 
```

## Immutable (Arrays)
```javascript
let immutableArray = [1, 2, 3];
let newArray = [...immutableArray, 4]; 
```

## Mutable (Strings)
```javascript
let mutableString = "Hello";
mutableString += " World"; 
```

## Immutable (Strings)
```javascript
let immutableString = "Hello";
let newString = immutableString + " World"; 
```


## Pass by Value (Primitive Types)
```javascript
let x = 5;
let y = x; 
x = 10;
console.log(y); // Output: 5
```

## Pass by Reference (Objects)
```javascript
let obj1 = { a: 1 };
let obj2 = obj1; 
obj1.a = 5;
console.log(obj2.a); // Output: 5
```


**Array Methods in JavaScript**

**Basics:**

- **Array.pop (Mutable):**
  ```javascript
  let array = [1, 2, 3];
  let poppedValue = array.pop(); 
  ```

- **Array.push (Mutable):**
  ```javascript
  let array = [1, 2, 3];
  array.push(4); 
  ```

- **Array.concat (Immutable):**
  ```javascript
  let array1 = [1, 2, 3];
  let array2 = [4, 5];
  let newArray = array1.concat(array2); 
  ```

- **Array.slice (Immutable):**
  ```javascript
  let array = [1, 2, 3, 4, 5];
  let slicedArray = array.slice(1, 4); 
  ```

- **Array.splice (Mutable):**
  ```javascript
  let array = [1, 2, 3, 4, 5];
  array.splice(2, 1); 
  ```

- **Array.join (Immutable):**
  ```javascript
  let array = [1, 2, 3];
  let joinedString = array.join('-');
  ```

- **Array.flat (Immutable):**
  ```javascript
  let nestedArray = [1, [2, [3, 4]]];
  let flatArray = nestedArray.flat(2); 
  ```

**Finding:**

- **Array.find:**
  ```javascript
  let array = [1, 2, 3, 4, 5];
  let foundValue = array.find(element => element > 2); 
  ```

- **Array.indexOf:**
  ```javascript
  let array = [1, 2, 3, 4, 5];
  let index = array.indexOf(3); 
  ```

- **Array.includes:**
  ```javascript
  let array = [1, 2, 3, 4, 5];
  let isPresent = array.includes(3); 
  ```

- **Array.findIndex:**
  ```javascript
  let array = [1, 2, 3, 4, 5];
  let index = array.findIndex(element => element > 2); 
  ```

**Higher Order Functions:**

- **Array.forEach (Mutable):**
  ```javascript
  let array = [1, 2, 3];
  array.forEach(element => console.log(element)); 
  ```

- **Array.filter (Immutable):**
  ```javascript
  let array = [1, 2, 3, 4, 5];
  let filteredArray = array.filter(element => element > 2); 
  ```

- **Array.map (Immutable):**
  ```javascript
  let array = [1, 2, 3];
  let mappedArray = array.map(element => element * 2); 
  ```

- **Array.reduce (Immutable):**
  ```javascript
  let array = [1, 2, 3, 4, 5];
  let sum = array.reduce((acc, curr) => acc + curr, 0); 
  ```

- **Array.sort (Mutable):**
  ```javascript
  let array = [3, 1, 4, 1, 5];
  array.sort((a, b) => a - b); 
  ```

**Advanced:**

- **Array Methods Chaining:**
  ```javascript
  let array = [1, 2, 3, 4, 5];
  let result = array
    .filter(element => element > 2)
    .map(element => element * 2)
    .reduce((acc, curr) => acc + curr, 0);
  ```


- **String.concat (Immutable):**
  ```javascript
  let str1 = 'Hello';
  let str2 = ' World';
  let newString = str1.concat(str2); 
  ```

- **String.slice (Immutable):**
  ```javascript
  let originalString = 'Hello World';
  let slicedString = originalString.slice(6, 11); 
  ```

- **String.toUpperCase (Immutable):**
  ```javascript
  let lowercase = 'hello';
  let uppercase = lowercase.toUpperCase(); 
  ```

- **String.replace (Immutable):**
  ```javascript
  let originalString = 'Hello World';
  let replacedString = originalString.replace('World', 'Universe'); 
  ```

- **String.trim (Immutable):**
  ```javascript
  let paddedString = '   Hello   ';
  let trimmedString = paddedString.trim(); 
  ```

- **String.charAt (Immutable):**
  ```javascript
  let str = 'Hello';
  let char = str.charAt(2); 
  ```

**Object Methods and Operations in JavaScript**

- **Object.assign (Immutable):**
  ```javascript
  let obj1 = { a: 1 };
  let obj2 = { b: 2 };
  let newObj = Object.assign({}, obj1, obj2); 
  ```

- **Object.keys (Immutable):**
  ```javascript
  let obj = { a: 1, b: 2, c: 3 };
  let keys = Object.keys(obj); 
  ```

- **Object.freeze (Mutable):**
  ```javascript
  let mutableObj = { x: 1, y: 2 };
  Object.freeze(mutableObj); 
  ```

- **Object.entries (Immutable):**
  ```javascript
  let obj = { a: 1, b: 2 };
  let entries = Object.entries(obj); 
  ```

- **Object.values (Immutable):**
  ```javascript
  let obj = { a: 1, b: 2, c: 3 };
  let values = Object.values(obj); 
  ```

- **Object.hasOwnProperty (Immutable):**
  ```javascript
  let obj = { a: 1, b: 2 };
  let hasProperty = obj.hasOwnProperty('a'); 
  ```

- **Object.delete (Mutable):**
  ```javascript
  let mutableObj = { x: 1, y: 2 };
  delete mutableObj.x; 
  ```

  **Hoisting in JavaScript:**

```javascript
console.log(x); 
var x = 5;
```

**Scopes in JavaScript:**

```javascript
function example() {
  if (true) {
    var localVar = 'I am local';
  }
  console.log(localVar); 
}
```

**Closures in JavaScript:**

```javascript
function outerFunction() {
  let outerVar = 'I am outer';

  function innerFunction() {
    console.log(outerVar); 
  }

  return innerFunction;
}

let closureExample = outerFunction();
closureExample(); 
```

**Higher Order Functions in JavaScript:**

```javascript
function multiplyBy(factor) {
  return function (number) {
    return number * factor;
  };
}

let multiplyByTwo = multiplyBy(2);
console.log(multiplyByTwo(5)); 
```

**Best Practices in JavaScript:**

- Use `const` and `let` instead of `var`.
- Prefer arrow functions for concise syntax.
- Avoid global variables.
- Use meaningful variable and function names.
- Embrace modular and reusable code.

**Debugging in JavaScript:**

- Use `console.log` for basic debugging.
- Utilize breakpoints and step-through in browser dev tools.
- Leverage `debugger` statement for pausing execution.
- Employ `try-catch` blocks for error handling.
- Consider using tools like ESLint and Prettier for code quality.
