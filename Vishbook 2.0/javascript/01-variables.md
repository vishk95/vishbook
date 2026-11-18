---
title: Variables
---

# JavaScript Variables

## Define Variables

A variable is a named container used to store data.

Variables can store:

- Strings
- Numbers
- Booleans
- Objects
- Arrays
- Functions

Example:

```js
let name = "Vishal";
```

---

## Syntax

### Declare and Initialize

```js
let a = 10;
const b = 20;
var c = 30;
```

### Declare First, Assign Later

```js
let x;
x = 5;
```

---

## let vs var

### let

- Block scoped
- Cannot be redeclared in the same scope
- Preferred in modern JavaScript

Example:

```js
let age = 25;

if (true) {
  let age = 30;
  console.log(age); // 30
}

console.log(age); // 25
```

### var

- Function scoped
- Can be redeclared
- Avoid using in modern JavaScript

Example:

```js
var count = 1;
var count = 2; // Allowed
```

---

## Best Practice

- Use `const` by default
- Use `let` when the value needs to change
- Avoid `var`

---

## Hoisting

JavaScript moves variable declarations to the top of their scope before execution.

### var

```js
console.log(x); // undefined

var x = 10;

console.log(x); // 10
```

### let / const

They are hoisted but not initialized.

Accessing them before declaration throws a `ReferenceError`.

```js
console.log(y); // ReferenceError

let y = 10;
```

---

## Why Hoisting Exists

Hoisting allows the JavaScript engine to know that a variable exists within a scope from the beginning of execution.

This prevents accidental access to outer-scope variables and helps detect errors early.

Example:

```js
var x = 10;

if (true) {
  console.log(x); // ReferenceError (TDZ)

  let x = 20;

  console.log(x); // 20
}
```

---

## Temporal Dead Zone (TDZ)

The TDZ is the period between:

1. Variable being hoisted ✅
2. Variable being initialized ❌

Accessing a variable during this period causes a `ReferenceError`.

Applies only to:

- let
- const

Example:

```js
console.log(a); // ReferenceError

let a = 5;
```

---

## Mutable vs Immutable

### let

Mutable.

```js
let city = "Bangalore";

city = "Mumbai";
```

### const

Cannot be reassigned.

```js
const country = "India";

country = "USA"; // Error
```

---

## Important Note About Objects and Arrays

`const` prevents reassignment of the variable reference.

It does NOT make the object immutable.

```js
const obj = {
  name: "Vishal"
};

obj.name = "Kardam"; // Allowed

console.log(obj.name);
```

Arrays behave similarly:

```js
const arr = [1, 2, 3];

arr.push(4); // Allowed
```