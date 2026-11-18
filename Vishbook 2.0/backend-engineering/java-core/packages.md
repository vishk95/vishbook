# Java Packages

## What is a Package?

A **package** is a way to group related classes, interfaces, enums, and other Java components.

Think of a package like a folder on your computer that helps organize files.

```text
com.company.app
    ├── Main.java
    ├── User.java
    └── Product.java
```

## Why Use Packages?

- Organize code
- Avoid class name conflicts
- Control access
- Improve maintainability

## Creating a Package

```java
package com.company.app;

public class User {
}
```

The package statement must be the first line in the file.

## Importing Classes

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> names = new ArrayList<>();
    }
}
```

## Common Java Packages

```text
java.lang
java.util
java.io
java.time
java.math
```

Examples:

```java
String       // java.lang
ArrayList    // java.util
LocalDate    // java.time
```

## Package Naming Convention

Typically based on a reversed domain name:

```text
com.google
com.microsoft
com.bp.energy
```

Example:

```java
package com.bp.salesforce.integration;
```

## Interview Definition

> A package is a namespace used to organize related Java classes and interfaces and avoid naming conflicts.

## One-Minute Revision

```text
Package
→ Organizes related classes
→ Prevents naming conflicts
→ Improves maintainability
```
