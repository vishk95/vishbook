# Classes and Objects in Java

## What are Classes and Objects?

Classes and Objects are the foundation of Object-Oriented Programming (OOP).

```text
Class  → Blueprint / Template
Object → Instance created from that blueprint
```

Real-world example:

```text
Class  → Car
Object → My Toyota
Object → Your Honda
Object → Someone's BMW
```

---

## What is a Class?

A class is a blueprint that defines:

- Attributes (data/state)
- Methods (behavior)

```java
public class Car {

    String brand;
    String color;

    void drive() {
        System.out.println("Driving...");
    }
}
```

### Fields (Attributes)

```java
String brand;
String color;
```

### Methods (Behavior)

```java
void drive()
```

---

## What is an Object?

An object is an actual instance of a class.

```java
Car car1 = new Car();
```

```text
Class Car
    ↓
new Car()
    ↓
Object created in memory
```

---

## Accessing Fields and Methods

```java
Car car1 = new Car();

car1.brand = "Toyota";
car1.color = "White";

car1.drive();
```

Output:

```text
Driving...
```

---

## Complete Example

```java
public class Car {

    String brand;
    String color;

    void display() {
        System.out.println(brand + " " + color);
    }

    public static void main(String[] args) {

        Car car1 = new Car();

        car1.brand = "Toyota";
        car1.color = "White";

        car1.display();
    }
}
```

Output:

```text
Toyota White
```

---

## Multiple Objects

```java
Car car1 = new Car();
Car car2 = new Car();
```

```java
car1.brand = "Toyota";
car2.brand = "Honda";
```

Each object maintains its own state.

---

## Constructors

A constructor initializes an object.

```java
public class Car {

    String brand;

    Car(String brand) {
        this.brand = brand;
    }
}
```

Creating objects:

```java
Car c1 = new Car("Toyota");
Car c2 = new Car("Honda");
```

---

## Memory View

```java
Car car1 = new Car();
```

```text
Stack                    Heap

car1 -------->  Car Object
               brand = null
               color = null
```

`car1` is a reference variable that points to an object in heap memory.

---

## Class vs Object

### Class

- Blueprint
- Logical entity
- Defined using the `class` keyword
- No instance memory until objects are created

### Object

- Instance of a class
- Physical entity
- Occupies memory
- Created using the `new` keyword

Example:

```text
Class  -> Student
Object -> Vishal
Object -> Rahul
Object -> Priya
```

---

## Real-World Example: Bank Account

```java
public class BankAccount {

    String accountNumber;
    double balance;

    void deposit(double amount) {
        balance += amount;
    }

    void withdraw(double amount) {
        balance -= amount;
    }
}
```

Creating objects:

```java
BankAccount a1 = new BankAccount();
BankAccount a2 = new BankAccount();

 a1.accountNumber = "123";
 a2.accountNumber = "456";
```

Each account maintains its own balance and account number.

---

## Why Use Classes and Objects?

Without OOP:

```java
String empName;
int empAge;
```

With OOP:

```java
Employee e1 = new Employee();
Employee e2 = new Employee();
Employee e3 = new Employee();
```

The same class can represent thousands of entities.

---

## Interview Questions

### What is a class?

> A class is a blueprint that defines the properties and behaviors of objects.

### What is an object?

> An object is an instance of a class that contains actual data and can invoke methods.

### What does the `new` keyword do?

> It creates an object in memory and returns a reference to it.

### Can a class exist without objects?

✅ Yes

```java
class Student {
}
```

### Can objects exist without a class?

❌ No

Every object must be created from a class.

---

## One-Minute Revision

```text
Class
    → Blueprint/Template

Object
    → Instance of a class

Fields
    → Data/State

Methods
    → Behavior

new
    → Creates an object

Constructor
    → Initializes an object
```

### Example

```java
class Student {
    String name;
}

Student s1 = new Student();
s1.name = "Vishal";
```

```text
Student -> Class
s1      -> Object
name    -> Field
new     -> Object creation
```
