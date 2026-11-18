# Java Access Modifiers

## What are Access Modifiers?

Access modifiers control who can access a class, method, field, or constructor.

Java provides four access levels:

```text
private
default
protected
public
```

## private

Accessible only within the same class.

```java
public class Employee {

    private String salary;

    public void printSalary() {
        System.out.println(salary);
    }
}
```

## default (Package-Private)

No modifier specified.

```java
class Employee {
    String name;
}
```

Accessible only within the same package.

## protected

Accessible:

- Within the same package
- In subclasses, even across packages

```java
public class Animal {

    protected void eat() {
        System.out.println("Eating");
    }
}
```

## public

Accessible from anywhere.

```java
public class User {

    public void login() {
        System.out.println("Login");
    }
}
```

## Access Modifier Summary

```text
private   → Same class only
default   → Same package only
protected → Same package + subclasses
public    → Everywhere
```

## Real-World Example

```java
public class BankAccount {

    private double balance;

    public void deposit(double amount) {
        balance += amount;
    }

    public double getBalance() {
        return balance;
    }
}
```

This is an example of encapsulation.

## Interview Questions

### Which access modifier is most restrictive?

`private`

### Which access modifier is least restrictive?

`public`

### Why make fields private?

To achieve encapsulation and protect object state.
