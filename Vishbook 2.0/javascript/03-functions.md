---
title: Functions
---

# JavaScript Functions – Structured Notes

## 1. What is a Function?

A **function** is a block of organized, reusable code used to perform a specific task.

### Key Behavior

- Functions always return a value.
- If nothing is returned, JavaScript returns `undefined`.

---

## 2. Parameters vs Arguments

| Term | Meaning |
|------|----------|
| Parameter | Variable in function definition |
| Argument | Value passed during function call |

```js
function add(a, b) { // parameters
  return a + b;
}

add(2, 3); // arguments
```

### Important

```js
2 + undefined; // NaN
```

Missing arguments can lead to `NaN`.

---

## 3. Arguments Object

Every regular function has an `arguments` object.

It contains all arguments passed to the function, even if they are not defined as parameters.

### Example

```js
function add() {
  console.log(arguments);

  let result = 0;

  for (const value of arguments) {
    result += value;
  }

  return result;
}

add(1, 2, 3);
add(1, 2, 3, 4, 5);
```

### Key Points

- Handles a variable number of arguments
- Acts as an array-like object

---

## 4. Scope

### 4.1 Function Scope

Variables declared inside a function are accessible only within that function.

### Scope Chain

When searching for a variable, JavaScript looks in:

1. Local scope
2. Parent scope
3. Global scope

If not found:

```js
ReferenceError
```

### Example

```js
function greetings() {
  let greeting = "Hello from function scope";

  function sayHi() {
    let greeting = "Hey from block scope";
    console.log(greeting);
  }

  sayHi();
  console.log(greeting);
}

greetings();
```

---

### 4.2 Block Scope

Block scope refers to variables declared within `{}` such as:

- `if`
- `for`
- `while`
- `switch`

### Important

- `let` and `const` are block scoped
- `var` is NOT block scoped

### Best Practice

- Prefer `let` and `const`
- Avoid using `var`

---

## 5. IIFE (Immediately Invoked Function Expression)

An IIFE executes immediately after it is defined.

### Example

```js
(function () {
  console.log("IIFE executed");
})();
```

### Benefits

- Avoids global variable pollution
- Provides encapsulation
- Creates a private scope

---

## 6. Closures

A closure allows a function to access variables from its outer scope even after the outer function has finished execution.

### Example

```js
function outer() {
  let count = 0;

  return function () {
    count++;
    return count;
  };
}

const counter = outer();

counter(); // 1
counter(); // 2
```

### Key Idea

The inner function remembers variables from its outer scope.

---

## 7. Function Expressions

A function can be assigned to a variable.

```js
const greet = function () {
  console.log("Hello");
};
```

### Common Uses

- Callbacks
- Dynamic behavior
- Higher-order functions

---

## 8. Arrow Functions (ES6)

### Features

- Shorter syntax
- More readable
- Lexical `this`

```js
const add = (a, b) => a + b;
```

### `this` Behavior

Arrow functions:

- Do not have their own `this`
- Inherit `this` from the enclosing scope

### No `arguments` Object

```js
const fn = () => {
  console.log(arguments); // ReferenceError
};
```

Use rest parameters instead:

```js
const fn = (...args) => {
  console.log(args);
};
```

### Short Syntax

```js
const square = x => x * x;
```

For a single expression, braces and `return` are optional.

### Important Note

Arrow functions are not a complete replacement for regular functions.

---

## 9. The `this` Keyword

`this` refers to the object that invokes the function.

### Behavior

- In a browser global function → `window`
- In an object method → the object itself

```js
const obj = {
  name: "JS",

  show() {
    console.log(this.name);
  }
};
```

### Key Point

The value of `this` depends on how the function is called.

---

## 10. Arrow Functions vs Regular Functions

### Arrow Functions

- Lexical `this`
- No `arguments`
- Cannot be used as constructors

### Regular Functions

- Own `this`
- Own `arguments`
- Can be used with `new`

---

## 11. Callback Functions

A callback function is a function passed as an argument to another function.

```js
function process(callback) {
  callback();
}

process(function () {
  console.log("Done");
});
```

### Key Point

A callback runs when the receiving function chooses to execute it.

---

## 12. Higher-Order Functions

Higher-order functions are functions that:

- Accept other functions as arguments
- Return functions

### Example

```js
function run(callback) {
  callback();
}

function createGreeting() {
  return function () {
    console.log("Hello");
  };
}
```

---

# Quick Revision Cheat Sheet

- Functions return `undefined` by default if nothing is returned
- Parameters vs Arguments
- `arguments` object
- Function scope
- Block scope
- `var` is not block scoped
- Closures retain outer variables
- IIFE creates isolated scope
- Arrow functions use lexical `this`
- Arrow functions do not have `arguments`
- `this` depends on invocation

---

# Interview Questions

1. What is the difference between parameters and arguments?
2. What happens if a function does not return anything?
3. Explain `arguments` object vs rest parameters.
4. What is the difference between function scope and block scope?
5. Why is `var` considered risky in modern JavaScript?
6. What is a closure? Provide an example.
7. What is the difference between arrow functions and regular functions?
8. What is an IIFE and why is it used?
9. What is a callback function?
10. What is a higher-order function?