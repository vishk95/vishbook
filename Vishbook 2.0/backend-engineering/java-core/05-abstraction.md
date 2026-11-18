---
title: Abstraction
---

# Java Abstraction

## What is Abstraction?

**Abstraction** is the process of hiding implementation details and exposing only the essential functionality to the user.

It focuses on:

```text
What an object does
NOT
How an object does it
```

### Definition

> Abstraction in Java hides internal implementation details and shows only the necessary features to the user. [1](https://www.geeksforgeeks.org/java/abstraction-in-java-2/)

---

# Why Do We Need Abstraction?

Without abstraction, users would need to understand every implementation detail.

With abstraction, users interact with a simple interface while the complexity remains hidden.

### Benefits

- Hides complexity
- Improves maintainability
- Reduces dependencies
- Improves security
- Makes systems easier to use and understand [1](https://www.geeksforgeeks.org/java/abstraction-in-java-2/)

---

# Real-Life Example

Consider a TV remote.

```text
User presses Power Button
          ↓
TV turns ON
```

The user does not need to know:

- Circuit design
- Signal processing
- Hardware operations

Only the required functionality is exposed. [1](https://www.geeksforgeeks.org/java/abstraction-in-java-2/)

---

# Ways to Achieve Abstraction in Java

Java provides two primary mechanisms:

1. Abstract Classes
2. Interfaces [1](https://www.geeksforgeeks.org/java/abstraction-in-java-2/)

---

# Abstract Classes

An abstract class is a class that:

- Cannot be instantiated
- May contain abstract methods
- May contain concrete methods
- May contain fields and constructors [1](https://www.geeksforgeeks.org/java/abstraction-in-java-2/)

## Syntax

```java
abstract class Shape {

    abstract double area();

    void display() {
        System.out.println("Shape");
    }
}
```

---

## Example

```java
abstract class Shape {

    abstract double area();
}

class Circle extends Shape {

    double radius = 5;

    @Override
    double area() {
        return Math.PI * radius * radius;
    }
}
```

Usage:

```java
Shape shape = new Circle();

System.out.println(shape.area());
```

---

## Key Points

- Supports partial abstraction
- Can contain implemented methods
- Useful when related classes share common behavior
- Uses the `abstract` keyword

---

# Interfaces

An interface defines a contract that implementing classes must follow.

Interfaces are used to achieve abstraction by defining behavior without implementation. [1](https://www.geeksforgeeks.org/java/abstraction-in-java-2/)

## Syntax

```java
interface Shape {

    double calculateArea();
}
```

---

## Example

```java
interface Shape {

    double calculateArea();
}

class Circle implements Shape {

    double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    public double calculateArea() {
        return Math.PI * radius * radius;
    }
}
```

Usage:

```java
Shape shape = new Circle(5);

System.out.println(shape.calculateArea());
```

---

## Key Points

- Defines behavior
- Supports multiple inheritance
- Implemented using the `implements` keyword
- May contain default and static methods (Java 8+) [1](https://www.geeksforgeeks.org/java/abstraction-in-java-2/)

---

# Abstract Class vs Interface

| Abstract Class | Interface |
|---------------|------------|
| Uses `extends` | Uses `implements` |
| Can have instance variables | Typically defines contracts |
| Can have constructors | Cannot have constructors |
| Supports partial abstraction | Supports behavior abstraction |
| Single inheritance | Multiple inheritance |

---

# Advantages of Abstraction

### 1. Reduces Complexity

Users interact only with relevant functionality.

### 2. Better Maintainability

Internal implementation can change without affecting users.

### 3. Improved Security

Sensitive implementation details remain hidden.

### 4. Loose Coupling

Different parts of the system become less dependent on each other. [1](https://www.geeksforgeeks.org/java/abstraction-in-java-2/)

---

# Disadvantages of Abstraction

- Can introduce extra complexity if overused
- May reduce implementation flexibility
- Makes debugging harder in some situations
- Excessive abstraction can make code harder to understand [1](https://www.geeksforgeeks.org/java/abstraction-in-java-2/)

---

# Common Mistakes

## Not Implementing Abstract Methods

```java
class Circle extends Shape {
    // Missing area() implementation
}
```

Must implement all abstract methods.

---

## Overusing Abstraction

Avoid making every class abstract unnecessarily.

Bad:

```text
Abstract everything
```

Good:

```text
Use abstraction only where it improves design
```

---

## Incorrect Method Signatures

The overridden method must match the abstract method exactly.

```java
abstract class Shape {
    abstract double area();
}
```

```java
class Circle extends Shape {

    @Override
    double area() {
        return 100;
    }
}
```

---

# Interview Questions

### What is abstraction?

> Abstraction is the process of hiding implementation details and exposing only essential functionality.

### How is abstraction achieved in Java?

```text
1. Abstract Classes
2. Interfaces
```

### Can we create an object of an abstract class?

```text
No
```

### Can abstract classes have constructors?

```text
Yes
```

### Which is better: Interface or Abstract Class?

```text
Interface:
    For defining contracts

Abstract Class:
    For sharing common implementation
```

---

# One-Minute Revision

```text
Abstraction
    → Hide implementation details

Goal
    → Focus on WHAT, not HOW

Achieved Using
    → Abstract Classes
    → Interfaces

Benefits
    → Simplicity
    → Maintainability
    → Security
    → Loose Coupling

Abstract Class
    → Partial abstraction
    → Can contain implementation

Interface
    → Contract
    → Multiple inheritance support
```

## Real-World Examples

```text
TV Remote
ATM Machine
Car Steering Wheel
Mobile Phone Apps
```

Users interact with functionality while the internal implementation remains hidden.