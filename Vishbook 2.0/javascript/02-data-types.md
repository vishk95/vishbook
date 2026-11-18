---
title: Data Types
---

# JavaScript Data Types, Type Conversion, and Operator Precedence

## JavaScript is Dynamically Typed

JavaScript is a **dynamically typed** language. This means the same variable can hold different types of values at different times.

```js
let message = "hello";
message = 123456;
```

No error occurs because JavaScript allows the variable type to change at runtime.

---

## JavaScript Data Types

JavaScript has:

- **7 primitive types**
- **1 non-primitive type**

---

## Primitive Types

Primitive values are simple, immutable values.

The 7 primitive types are:

1. `number`
2. `bigint`
3. `string`
4. `boolean`
5. `null`
6. `undefined`
7. `symbol`

---

## 1. Number

Used for integers and floating-point numbers.

```js
let age = 30;
let price = 99.99;
```

Special number values:

```js
Infinity;
-Infinity;
NaN; // Not a Number
```

Examples:

```js
console.log(10 / 0);      // Infinity
console.log(-10 / 0);     // -Infinity
console.log("abc" / 2);   // NaN
```

Important point:

```js
console.log(typeof NaN); // "number"
```

Even though `NaN` means "Not a Number", its type is still `number`.

---

## 2. BigInt

Used for very large integers beyond the safe limit of `number`.

```js
const bigNumber = 123456789012345678901234567890n;
console.log(typeof bigNumber); // "bigint"
```

A `BigInt` value ends with `n`.

---

## 3. String

Used for text.

```js
let firstName = "Vishal";
let city = 'Bangalore';
let message = `Hello ${firstName}`;
```

Strings can be created using:

- Double quotes: `"Hello"`
- Single quotes: `'Hello'`
- Backticks/template literals: `` `Hello` ``

---

## 4. Boolean

Used for true/false values.

```js
let isActive = true;
let isLoggedIn = false;
```

Commonly used in conditions:

```js
if (isActive) {
  console.log("User is active");
}
```

---

## 5. Null

`null` represents an intentional empty value.

```js
let selectedUser = null;
```

Important JavaScript quirk:

```js
console.log(typeof null); // "object"
```

This is a long-standing JavaScript bug/quirk.

---

## 6. Undefined

`undefined` means a variable has been declared but not assigned a value.

```js
let score;
console.log(score);        // undefined
console.log(typeof score); // "undefined"
```

---

## 7. Symbol

`Symbol` creates a unique value.

```js
const id1 = Symbol("id");
const id2 = Symbol("id");

console.log(id1 === id2); // false
```

Even if two symbols have the same description, they are unique.

---

## Non-Primitive Type

## Object

Objects are used to store collections of data and more complex entities.

Examples:

```js
const user = {
  name: "Vishal",
  age: 30
};

const numbers = [1, 2, 3];

function greet() {
  console.log("Hello");
}
```

In JavaScript, arrays and functions are also object-like values.

```js
console.log(typeof {});           // "object"
console.log(typeof []);           // "object"
console.log(typeof function () {}); // "function"
```

---

# typeof Operator

`typeof` is an operator used to check the type of a value.

```js
console.log(typeof 123);          // "number"
console.log(typeof "JS");         // "string"
console.log(typeof true);         // "boolean"
console.log(typeof undefined);    // "undefined"
console.log(typeof null);         // "object"
console.log(typeof NaN);          // "number"
console.log(typeof {});           // "object"
console.log(typeof []);           // "object"
console.log(typeof function () {}); // "function"
```

You may also see this syntax:

```js
typeof(123);
```

It works, but `typeof` is an operator, not a function.

Preferred style:

```js
typeof 123;
```

---

# Type Conversion

JavaScript can convert values from one type to another.

There are two types of conversion:

1. Explicit conversion
2. Implicit conversion/type coercion

---

## Explicit Conversion

You manually convert a value.

```js
String(123);       // "123"
Number("123");    // 123
Number("abc");    // NaN
Boolean("");      // false
Boolean("hello"); // true
Boolean(0);        // false
Boolean(1);        // true
```

---

## Implicit Conversion

JavaScript automatically converts values based on the context.

A simple way to remember:

> First JavaScript decides what to execute based on precedence, then it decides how to convert based on the operator/context.

Ask yourself:

- Is it a string operation? Convert to string.
- Is it a math operation? Convert to number.
- Is it a condition? Convert to boolean.

---

## Conversion by Context

| Context | Conversion Type |
|---|---|
| Display/output/concatenation | String |
| Mathematical operations | Number |
| Conditions/logical operations | Boolean |

---

## String Context

Using `+` with a string usually converts the other value to a string.

```js
console.log("hello" + 5); // "hello5"
console.log("1" + 2);     // "12"
```

---

## Number Context

Math operators usually convert values to numbers.

Operators:

- `-`
- `*`
- `/`
- `%`

Examples:

```js
console.log("6" / "2");  // 3
console.log("10" - "5"); // 5
console.log("5" * "2");  // 10
```

---

## Boolean Context

Conditions convert values to booleans.

Common boolean contexts:

- `if`
- `while`
- `&&`
- `||`
- `!`

Examples:

```js
if ("hello") {
  console.log("truthy");
}

if (0) {
  console.log("will not run");
}
```

---

# Truthy and Falsy Values

## Falsy Values

These values convert to `false`:

```js
false
0
-0
0n
""
null
undefined
NaN
```

Examples:

```js
Boolean(false);     // false
Boolean(0);         // false
Boolean("");        // false
Boolean(null);      // false
Boolean(undefined); // false
Boolean(NaN);       // false
```

## Truthy Values

Everything else is truthy.

Examples:

```js
Boolean("hello"); // true
Boolean(1);       // true
Boolean([]);      // true
Boolean({});      // true
```

Important:

```js
Boolean([]); // true
Boolean({}); // true
```

Empty arrays and empty objects are truthy.

---

# Special Case: The `+` Operator

The `+` operator behaves differently depending on operands.

## Case 1: String Present

If any operand is a string, `+` performs string concatenation.

```js
console.log(1 + "2"); // "12"
```

## Case 2: No String Present

If no operand is a string, `+` performs numeric addition.

```js
console.log(1 + 2); // 3
```

---

## Important Type Conversion Edge Cases

```js
console.log("" + 1 + 0); // "10"
console.log(1 + 0 + ""); // "1"
console.log("5" - 2);    // 3
console.log("5" + 2);    // "52"
console.log("5" * 2);    // 10
console.log("5" / 2);    // 2.5
```

Why?

```js
"" + 1 + 0
```

Step-by-step:

```js
"" + 1 // "1"
"1" + 0 // "10"
```

---

# JavaScript Operator Precedence

Operator precedence determines the order in which operators are evaluated.

Higher-precedence operators run first.

---

## Precedence vs Associativity

## Precedence

Precedence decides **which operator runs first**.

Example:

```js
console.log(3 + 4 * 5); // 23
```

Multiplication runs before addition.

## Associativity

Associativity decides **direction of evaluation when operators have the same precedence**.

Common directions:

- Left-to-right
- Right-to-left

Example:

```js
console.log(100 / 10 / 2); // 5
```

Division is left-to-right:

```js
(100 / 10) / 2
```

---

# Important Operator Precedence Order

From high to low:

1. Grouping: `()`
2. Member access/function call: `.`, `[]`, `()`
3. Postfix increment/decrement: `x++`, `x--`
4. Unary operators: `!`, `typeof`, `delete`, unary `+`, unary `-`, `++x`, `--x`
5. Exponentiation: `**`
6. Multiplicative: `*`, `/`, `%`
7. Additive: `+`, `-`
8. Bitwise shift: `<<`, `>>`, `>>>`
9. Relational/comparison: `<`, `<=`, `>`, `>=`, `in`, `instanceof`
10. Equality: `==`, `!=`, `===`, `!==`
11. Bitwise AND: `&`
12. Bitwise XOR: `^`
13. Bitwise OR: `|`
14. Logical AND: `&&`
15. Logical OR: `||`
16. Nullish coalescing: `??`
17. Conditional/ternary: `condition ? a : b`
18. Assignment: `=`, `+=`, `-=`, `*=`, `/=`
19. Comma: `,`

---

# Quick Precedence Ladder

```txt
()
member access / function call
x++ x--
! typeof delete unary + unary - ++x --x
**
* / %
+ -
<< >> >>>
< <= > >= in instanceof
== != === !==
&
^
|
&&
||
??
?:
= += -= *= /=
,
```

---

# JavaScript Operator Precedence and Associativity Examples

## 1. Parentheses Override Precedence

```js
console.log(3 + 4 * 5);       // 23
console.log((3 + 4) * 5);     // 35
console.log(3 + (4 * 5));     // 23
```

---

## 2. Multiplication, Division, and Remainder Before Addition/Subtraction

```js
console.log(10 + 20 / 5);     // 14
console.log(10 - 2 * 3);      // 4
console.log(20 % 6 + 2);      // 4
console.log(2 + 3 * 4 - 5);   // 9
console.log((2 + 3) * (4 - 5)); // -5
```

---

## 3. Same Precedence: Left-to-Right Associativity

```js
console.log(100 / 10 / 2); // 5
console.log(10 - 3 - 2);   // 5
console.log(2 * 3 * 4);    // 24
console.log(20 / 2 * 5);   // 50
console.log(20 % 6 % 2);   // 0
```

---

## 4. Exponentiation is Right-to-Left

```js
console.log(2 ** 3 ** 2);     // 512
console.log((2 ** 3) ** 2);   // 64
console.log(2 ** (3 ** 2));   // 512
console.log(4 ** 3 ** 2);     // 262144
```

---

## 5. Exponentiation Before Multiplication/Division

```js
console.log(2 * 3 ** 2);      // 18
console.log(2 ** 3 * 2);      // 16
console.log(2 ** 3 / 4);      // 2
console.log(2 ** 3 / 3 ** 2); // 0.8888888888888888
```

---

## 6. Unary Operators Before Binary Operators

```js
console.log(-5 + 10);                  // 5
console.log(+true + 5);                // 6
console.log(+false + 5);               // 5
console.log(!false === true);          // true
console.log(typeof 123 + " value");    // "number value"
console.log(typeof "JS" === "string"); // true
console.log(!true || false);           // false
```

---

## 7. Unary Minus with Exponentiation Pitfall

```js
// console.log(-2 ** 2); // SyntaxError
console.log(-(2 ** 2));  // -4
console.log((-2) ** 2);  // 4
```

---

## 8. Postfix and Prefix Increment/Decrement

```js
let x1 = 5;
let y1 = x1++;

console.log(x1); // 6
console.log(y1); // 5

let x2 = 5;
let y2 = ++x2;

console.log(x2); // 6
console.log(y2); // 6
```

More examples:

```js
let a1 = 1;
let result1 = a1++ + ++a1;

console.log(result1); // 4
console.log(a1);      // 3

let b1 = 5;
console.log(b1++); // 5
console.log(b1);   // 6

let b2 = 5;
console.log(++b2); // 6
console.log(b2);   // 6
```

---

## 9. Function Call and Member Access

```js
const user = {
  name: "Vishal",
  getName() {
    return this.name;
  }
};

console.log(user.getName());                 // "Vishal"
console.log(user.getName().toUpperCase());   // "VISHAL"
console.log(Math.max(2, 3) + 10);            // 13
console.log("javascript".toUpperCase().length); // 10
```

---

## 10. Addition vs String Concatenation

```js
console.log(1 + 2 + "3");     // "33"
console.log("1" + 2 + 3);     // "123"
console.log("5" + 2 * 3);     // "56"
console.log(("5" + 2) * 3);   // 156
console.log(5 + "2" * 3);     // 11
console.log("5" + 2 - 3);     // 49
console.log("5" - 2 + 3);     // 6
console.log("5" + 2 + 3);     // "523"
console.log(5 + 2 + "3");     // "73"
```

---

## 11. Numeric Conversion with `-`, `*`, and `/`

```js
console.log("10" - "4");  // 6
console.log("10" * "4");  // 40
console.log("10" / "2");  // 5
console.log("10" + "4");  // "104"
console.log("10" - true); // 9
console.log("10" + true); // "10true"
console.log(false + 5);   // 5
console.log(true + true); // 2
```

---

## 12. Comparison Before Equality

```js
console.log(5 > 3 === true);  // true
console.log(5 < 3 === false); // true
console.log(10 > 5 == true);  // true
console.log(10 < 5 == false); // true
```

---

## 13. Chained Comparison Pitfalls

```js
console.log(3 > 2 > 1);      // false
console.log(1 < 2 < 3);      // true
console.log(3 > 2 > 0);      // true
console.log(5 > 4 > 3);      // false
console.log(5 > 4 && 4 > 3); // true
```

Explanation:

```js
3 > 2 > 1
```

Step-by-step:

```js
true > 1
1 > 1
false
```

---

## 14. Equality and Type Coercion

```js
console.log(0 == false);        // true
console.log(0 === false);       // false
console.log(null == undefined); // true
console.log(null === undefined); // false
console.log("5" == 5);          // true
console.log("5" === 5);         // false
console.log("" == 0);           // true
console.log("" === 0);          // false
console.log(false == "0");      // true
console.log(false === "0");     // false
```

Best practice:

```js
// Prefer strict equality
===
!==
```

---

## 15. Logical AND Has Higher Precedence Than Logical OR

```js
console.log(true || false && false);     // true
console.log((true || false) && false);   // false
console.log(false || true && true);      // true
console.log(false && true || true);      // true
console.log(true && false || true);      // true
console.log(true || false || false && false); // true
```

---

## 16. Logical Operators Return Actual Values

Logical operators do not always return `true` or `false`. They return actual operand values.

```js
console.log("hello" && "world"); // "world"
console.log(0 && "hello");       // 0
console.log("hello" || "world"); // "hello"
console.log(0 || "" || "default"); // "default"
console.log(null || "A" && "B"); // "B"
console.log("A" && null && "B"); // null
console.log("A" || null || "B"); // "A"
console.log(false || 0 || "JS");  // "JS"
```

---

## 17. Logical Associativity is Left-to-Right

```js
console.log(true && false && true);  // false
console.log(true && true && "done"); // "done"
console.log(false || 0 || "JS");     // "JS"
console.log("A" && "B" && "C");      // "C"
console.log(null || undefined || "X"); // "X"
```

---

## 18. Nullish Coalescing

The nullish coalescing operator `??` returns the right-hand value only when the left-hand value is `null` or `undefined`.

```js
console.log(null ?? "default");      // "default"
console.log(undefined ?? "default"); // "default"
console.log(0 ?? "default");         // 0
console.log("" ?? "default");        // ""
console.log(false ?? "default");     // false
console.log(NaN ?? "default");       // NaN
```

---

## 19. Nullish Coalescing vs Logical OR

`||` checks for falsy values.

`??` checks only for `null` or `undefined`.

```js
console.log(0 || "default");      // "default"
console.log(0 ?? "default");      // 0

console.log("" || "default");     // "default"
console.log("" ?? "default");     // ""

console.log(false || "default");  // "default"
console.log(false ?? "default");  // false
```

---

## 20. Cannot Mix `??` with `||` or `&&` Without Parentheses

```js
// console.log(null || undefined ?? "default"); // SyntaxError
console.log((null || undefined) ?? "default"); // "default"
console.log(null || (undefined ?? "default")); // "default"

// console.log(true && null ?? "value"); // SyntaxError
console.log((true && null) ?? "value"); // "value"
console.log(true && (null ?? "value")); // "value"
```

---

## 21. Ternary Operator Precedence

```js
console.log(true || false ? "A" : "B");   // "A"
console.log(false || false ? "A" : "B");  // "B"
console.log(true && false ? "A" : "B");   // "B"
console.log(5 > 3 ? "yes" : "no");        // "yes"
console.log(5 < 3 ? "yes" : "no");        // "no"
```

---

## 22. Ternary is Right-to-Left Associative

```js
console.log(true ? "A" : false ? "B" : "C");  // "A"
console.log(false ? "A" : true ? "B" : "C");  // "B"
console.log(false ? "A" : false ? "B" : "C"); // "C"
```

---

## 23. Assignment is Right-to-Left Associative

```js
let c1;
let c2;

c1 = c2 = 5;

console.log(c1); // 5
console.log(c2); // 5
```

More example:

```js
let d1 = 1;
let d2 = 2;
let d3 = 3;

d1 = d2 = d3 = 10;

console.log(d1); // 10
console.log(d2); // 10
console.log(d3); // 10
```

---

## 24. Assignment Has Lower Precedence Than Arithmetic

```js
let e1;
e1 = 2 + 3 * 4;
console.log(e1); // 14

let e2 = 5;
e2 += 2 * 3;
console.log(e2); // 11

let e3 = 10;
e3 -= 4 / 2;
console.log(e3); // 8
```

---

## 25. Compound Assignment Also Follows Right-to-Left Behavior

```js
let f1 = 1;
let f2 = 2;

let result2 = f1 += f2 *= 3;

console.log(f1);      // 7
console.log(f2);      // 6
console.log(result2); // 7
```

---

## 26. Comma Operator

The comma operator evaluates multiple expressions and returns the last one.

```js
let g1 = (1, 2, 3);
console.log(g1); // 3

let h1 = 1;
let h2 = 2;

let result3 = (h1++, h2++, h1 + h2);

console.log(result3); // 5
console.log(h1);      // 2
console.log(h2);      // 3
```

---

## 27. Bitwise Shift Operators

```js
console.log(1 << 2);     // 4
console.log(1 << 2 + 1); // 8
console.log(8 >> 1 + 1); // 2
console.log(16 >> 2);    // 4
console.log(5 << 1);     // 10
```

---

## 28. Bitwise AND, XOR, and OR Precedence

```js
console.log(5 | 3 & 1);   // 5
console.log(5 ^ 3 & 1);   // 4
console.log(5 | 3 ^ 1);   // 7
console.log((5 | 3) & 1); // 1
console.log(5 & 3 | 1);   // 1
```

---

## 29. Logical vs Bitwise Operators

```js
console.log(true && false); // false
console.log(true & false);  // 0

console.log(true || false); // true
console.log(true | false);  // 1

console.log(5 && 3); // 3
console.log(5 & 3);  // 1

console.log(5 || 3); // 5
console.log(5 | 3);  // 7
```

---

## 30. Optional Chaining

Optional chaining `?.` safely accesses nested properties.

```js
const user1 = null;
console.log(user1?.name); // undefined

const user2 = {
  profile: {
    name: "Vishal"
  }
};

console.log(user2?.profile?.name); // "Vishal"

const user3 = {
  profile: null
};

console.log(user3?.profile?.name); // undefined

// console.log(user3?.profile.name); // TypeError
```

---

## 31. More typeof Examples

```js
console.log(typeof 123);          // "number"
console.log(typeof "JS");         // "string"
console.log(typeof true);         // "boolean"
console.log(typeof undefined);    // "undefined"
console.log(typeof null);         // "object"
console.log(typeof NaN);          // "number"
console.log(typeof {});           // "object"
console.log(typeof []);           // "object"
console.log(typeof function () {}); // "function"
```

---

## 32. delete with Member Access

```js
const obj1 = {
  name: "Vishal",
  age: 30
};

console.log(delete obj1.name);         // true
console.log(obj1);                     // { age: 30 }
console.log(delete obj1.age === true); // true
```

---

## 33. new with Member Access/Function Call

```js
console.log(new Date().getFullYear()); // current year

// Invalid/unsafe usage:
// console.log(new Date.getFullYear());
```

---

## 34. Spread Syntax Examples

```js
const arr1 = [1, 2];
const arr2 = [...arr1, 3];

console.log(arr2); // [1, 2, 3]

const obj2 = { a: 1 };
const obj3 = { ...obj2, b: 2 };

console.log(obj3); // { a: 1, b: 2 }
```

---

## 35. Destructuring Assignment

Array destructuring:

```js
let i1;
let i2;

[i1, i2] = [1, 2];

console.log(i1); // 1
console.log(i2); // 2
```

Object destructuring:

```js
let i3;

({ i3 } = { i3: 10 });

console.log(i3); // 10
```

---

## 36. Mixed Expression Examples

```js
console.log(2 + 3 * 4 > 10 && false || true); // true
console.log("5" + 3 * 2 == "56");             // true
console.log("5" - 2 + 3);                     // 6
console.log("5" + 2 - 3);                     // 49
console.log(true + true * false);             // 1
console.log(!true || false && true);          // false
```

---

## 37. More Mixed Type Coercion and Precedence Examples

```js
console.log([] + []);     // ""
console.log([] + {});     // "[object Object]"
console.log({} + []);     // "[object Object]" in many console contexts
console.log(+[]);         // 0
console.log(+{});         // NaN
console.log(![]);         // false
console.log(!![]);        // true
console.log(!{});         // false
console.log(!!{});        // true
```

---

## 38. Boolean Conversion with Logical Operators

```js
console.log(Boolean(0 || "A"));       // true
console.log(Boolean("" && "A"));      // false
console.log(Boolean("A" && "B"));     // true
console.log(Boolean(null ?? "A"));    // true
```

---

## 39. Pitfall with Default Values

Using `||` can accidentally replace valid falsy values like `0`, `""`, and `false`.

```js
let count1 = 0;

console.log(count1 || 10); // 10
console.log(count1 ?? 10); // 0

let name1 = "";

console.log(name1 || "Guest"); // "Guest"
console.log(name1 ?? "Guest"); // ""
```

Use `??` when only `null` or `undefined` should trigger the default value.

---

## 40. Practical Safe Examples Using Parentheses

```js
console.log(("5" + 2) * 3);          // 156
console.log("5" + (2 * 3));          // "56"
console.log((true || false) && false); // false
console.log(true || (false && false)); // true
console.log((null ?? "A") || "B");    // "A"
console.log(null ?? ("A" || "B"));    // "A"
```

---

# Quick Revision Summary

## Data Types

- JavaScript has 7 primitive types and 1 main non-primitive type.
- Primitive types are immutable.
- Objects are reference values.
- Arrays and functions are object-like values.

## typeof

Important results to remember:

```js
typeof null;      // "object"
typeof NaN;       // "number"
typeof [];        // "object"
typeof {};        // "object"
typeof function() {}; // "function"
```

## Type Conversion

- `+` can mean addition or string concatenation.
- `-`, `*`, `/`, and `%` usually convert values to numbers.
- Conditions convert values to booleans.
- `||` works with falsy values.
- `??` works only with `null` and `undefined`.

## Operator Precedence

Remember this high-level order:

```txt
()
function/member access
unary
**
* / %
+ -
comparison
equality
&&
||
??
?:
assignment
comma
```

---

# Practice Questions

1. What are the 7 primitive types in JavaScript?
2. Why does `typeof null` return `"object"`?
3. What is the difference between `null` and `undefined`?
4. What is the output of `"5" + 2`?
5. What is the output of `"5" - 2`?
6. Why does `3 > 2 > 1` return `false`?
7. What is the difference between `==` and `===`?
8. What is the difference between `||` and `??`?
9. Why is `[]` truthy?
10. What does optional chaining `?.` do?
