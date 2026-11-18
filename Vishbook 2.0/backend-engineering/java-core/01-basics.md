---
title: Java Quick Recap
---

# Java Quick Recap

## 1. Variables

A **variable** stores data in memory.

```java
int age = 25;
String name = "Vishal";
```

- `age` → variable name
- `25` → value
- `int` → data type

---

## 2. Data Types

### Primitive Types

```java
byte b = 10;
short s = 100;
int i = 1000;
long l = 100000L;

float f = 10.5f;
double d = 10.5;

char c = 'A';
boolean flag = true;
```

### Reference Types

```java
String name = "BP";
int[] numbers = {1, 2, 3};
```

---

## 3. Operators

### Arithmetic Operators

```java
int a = 10;
int b = 5;

a + b; // 15
a - b; // 5
a * b; // 50
a / b; // 2
a % b; // 0
```

### Comparison Operators

```java
a == b
a != b
a > b
a < b
a >= b
a <= b
```

### Logical Operators

```java
&&  // AND
||  // OR
!   // NOT
```

Example:

```java
int age = 25;

if(age > 18 && age < 60) {
    System.out.println("Working age");
}
```

---

## 4. Conditionals

### if

```java
int age = 20;

if(age >= 18) {
    System.out.println("Adult");
}
```

### if-else

```java
if(age >= 18) {
    System.out.println("Adult");
} else {
    System.out.println("Minor");
}
```

### if-else-if

```java
int marks = 85;

if(marks >= 90) {
    System.out.println("A");
} else if(marks >= 80) {
    System.out.println("B");
} else {
    System.out.println("C");
}
```

### switch

```java
String day = "MON";

switch(day) {
    case "MON":
        System.out.println("Monday");
        break;
    case "TUE":
        System.out.println("Tuesday");
        break;
    default:
        System.out.println("Unknown");
}
```

---

## 5. Loops

### for Loop

```java
for(int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

Output:

```text
1
2
3
4
5
```

### while Loop

```java
int i = 1;

while(i <= 5) {
    System.out.println(i);
    i++;
}
```

### do-while Loop

Runs at least once.

```java
int i = 1;

do {
    System.out.println(i);
    i++;
} while(i <= 5);
```

### Enhanced for Loop (For-Each)

```java
int[] nums = {10, 20, 30};

for(int num : nums) {
    System.out.println(num);
}
```

---

## 6. Arrays

An array stores multiple values of the same type.

```java
int[] numbers = {10, 20, 30, 40};
```

### Access Elements

```java
System.out.println(numbers[0]); // 10
System.out.println(numbers[2]); // 30
```

### Loop Through Array

```java
for(int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```

Or:

```java
for(int num : numbers) {
    System.out.println(num);
}
```

---

## 7. Methods

A method is a reusable block of code.

### Method with Return Value

```java
public static int add(int a, int b) {
    return a + b;
}
```

Usage:

```java
int result = add(10, 20);

System.out.println(result);
```

Output:

```text
30
```

### Void Method

```java
public static void greet() {
    System.out.println("Hello");
}
```

Usage:

```java
greet();
```

---

# Mini Example Combining Everything

```java
public class Main {

    public static int sum(int[] nums) {
        int total = 0;

        for(int num : nums) {
            total += num;
        }

        return total;
    }

    public static void main(String[] args) {

        int[] numbers = {10, 20, 30};

        int total = sum(numbers);

        if(total > 50) {
            System.out.println("Greater than 50");
        } else {
            System.out.println("50 or less");
        }

        System.out.println(total);
    }
}
```

---

# Interview Quick Definitions

- **Variable** → Named memory location that stores a value.
- **Data Type** → Defines what kind of data a variable can hold.
- **Operator** → Symbol used to perform operations on values.
- **Conditional** → Controls program flow based on conditions (`if`, `switch`).
- **Loop** → Repeats a block of code (`for`, `while`, `do-while`).
- **Array** → Fixed-size collection of elements of the same type.
- **Method** → Reusable block of code that performs a specific task.

---

# One-Minute Revision

```text
Variables      → Store data
Data Types     → Define the type of data
Operators      → Perform calculations and comparisons
Conditionals   → Make decisions (if/switch)
Loops          → Repeat actions
Arrays         → Store multiple values
Methods        → Reusable functions
```