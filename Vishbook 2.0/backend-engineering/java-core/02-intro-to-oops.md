# OOP in Java

Object-Oriented Programming (OOP) is a programming paradigm that organizes software around **objects**, which contain **data (state)** and **methods (behavior)**.

```java
class Car {
    String brand;

    void drive() {
        System.out.println("Driving");
    }
}
```

---

# Encapsulation

Encapsulation means **hiding internal data** and providing controlled access through methods.

```java
class BankAccount {

    private double balance;

    public void deposit(double amount) {
        balance += amount;
    }

    public double getBalance() {
        return balance;
    }
}
```

### Key Points

- Uses `private` fields
- Protects data from direct modification
- Improves maintainability and security

**Example:** `BankAccount`

---

# Inheritance

Inheritance allows one class to **reuse properties and methods** of another class.

```java
class Animal {

    void eat() {
        System.out.println("Eating");
    }
}

class Dog extends Animal {

    void bark() {
        System.out.println("Barking");
    }
}
```

### Key Points

- Uses `extends`
- Promotes code reuse
- Creates an **IS-A** relationship

**Example:** `Dog IS-A Animal`

---

# Polymorphism

Polymorphism means **one interface, many forms**.

The same method call can behave differently depending on the object.

```java
class Animal {
    void makeSound() {
        System.out.println("Animal Sound");
    }
}

class Dog extends Animal {

    @Override
    void makeSound() {
        System.out.println("Bark");
    }
}
```

```java
Animal animal = new Dog();
animal.makeSound();
```

Output:

```text
Bark
```

### Types

- Method Overloading (Compile-Time)
- Method Overriding (Runtime)

---

# Abstraction

Abstraction means **hiding implementation details** and exposing only essential functionality.

```java
abstract class Shape {

    abstract double area();
}
```

```java
class Circle extends Shape {

    double radius = 5;

    double area() {
        return Math.PI * radius * radius;
    }
}
```

### Key Points

- Focus on "what" rather than "how"
- Reduces complexity
- Often implemented using abstract classes and interfaces

---

# Interfaces

An interface defines a **contract** that implementing classes must follow.

```java
interface Flyable {
    void fly();
}
```

```java
class Bird implements Flyable {

    public void fly() {
        System.out.println("Flying");
    }
}
```

### Key Points

- Uses `interface`
- Supports multiple inheritance
- Defines behavior without implementation

**Example:** `Runnable`, `Comparable`, `List`

---

# Abstract Classes

An abstract class is a partially implemented class that serves as a base class.

```java
abstract class Vehicle {

    abstract void move();

    void startEngine() {
        System.out.println("Engine Started");
    }
}
```

```java
class Car extends Vehicle {

    @Override
    void move() {
        System.out.println("Car Moving");
    }
}
```

### Key Points

- Can contain abstract and concrete methods
- Can have fields and constructors
- Supports code sharing among subclasses

---

# Interface vs Abstract Class

## Interface

```text
Used for capability/contract
"CAN DO"
```

Example:

```text
Bird CAN Fly
Duck CAN Swim
```

## Abstract Class

```text
Used for common base behavior
"IS A"
```

Example:

```text
Car IS A Vehicle
Dog IS A Animal
```

---

# Composition vs Inheritance

## Inheritance (IS-A)

```java
class Dog extends Animal {
}
```

```text
Dog IS-A Animal
```

Use inheritance when a true parent-child relationship exists.

---

## Composition (HAS-A)

```java
class Engine {

    void start() {
        System.out.println("Started");
    }
}

class Car {

    private Engine engine = new Engine();

    void startCar() {
        engine.start();
    }
}
```

```text
Car HAS-A Engine
```

### Why Composition is Preferred

- Looser coupling
- More flexible
- Easier to maintain
- Easier to replace implementations

---

# Quick Revision

```text
Encapsulation
→ Hide data using private fields

Inheritance
→ Reuse code using extends

Polymorphism
→ One method, many forms

Abstraction
→ Hide implementation details

Interface
→ Contract (CAN DO)

Abstract Class
→ Shared base implementation (IS A)

Composition
→ HAS-A relationship

Inheritance
→ IS-A relationship
```

## Interview Examples

```text
BankAccount       → Encapsulation
Dog extends Animal → Inheritance
Animal a = new Dog() → Polymorphism
Shape → Circle      → Abstraction
Runnable            → Interface
Vehicle             → Abstract Class
Car HAS-A Engine    → Composition
```