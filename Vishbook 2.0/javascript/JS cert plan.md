---
title: JS certification roadmap
---

# JavaScript Certification Study Plan

## JavaScript Basics (~20%)

1. Variables & Scope
2. Primitive Data Types
3. Operators
4. Functions
   - Scope
   - Closures
5. Objects & Prototypes
6. Error Handling (`try/catch`)

---

## Advanced JavaScript Concepts (~25%)

### Asynchronous JavaScript

- Callbacks
- Promises
- Promise Chaining
- Async/Await

### Execution Model

- Event Loop
- Call Stack
- Execution Context

### this Keyword

- Global context
- Object context
- Arrow functions

### Prototypes & Inheritance

- Prototype chain
- Constructor functions
- ES6 classes

### ES6+ Features

- Destructuring
- Spread operator
- Rest parameters
- Template literals
- Modules (`import` / `export`)

---

## Browser & DOM Manipulation (~20%)

### DOM

- DOM selection
- DOM traversal
- DOM modification

### Events

- Event handling
- Event bubbling
- Event capturing

### Styling

- Manipulating HTML
- Manipulating CSS

### Browser APIs

- Local Storage
- Session Storage
- Timers

---

## Asynchronous Data Handling & APIs (~15%)

### Fetch API

- GET requests
- POST requests

### JSON

- Parse JSON
- Stringify JSON

### REST APIs

- HTTP methods
- Status codes

### Error Handling

- API failures
- Network failures

---

## JavaScript in Salesforce (LWC Focus) (~10%)

### LWC Fundamentals

- JavaScript in LWC
- Data binding
- Component lifecycle

### Decorators

- `@track`
- `@api`
- `@wire`

### Events

- Parent-to-child communication
- Child-to-parent communication
- Custom events

### Apex Integration

- Wire adapters
- Imperative Apex calls

---

## Server-Side JavaScript

### Node.js Basics

- What is Node.js?
- V8 Engine
- Runtime Environment

### Architecture

- Event-driven architecture
- Non-blocking I/O

### Browser vs Server JavaScript

- Environment differences
- Available APIs

### Globals

- `process`
- `__dirname`
- `__filename`

### Modules

- CommonJS
- ES Modules

### Built-in Modules

- `fs`
- `path`
- `os`

### npm

- package.json
- Dependencies
- Scripts

### Error Handling

- try/catch
- Promise rejection handling

### Event Loop

- Call Stack
- Event Queue
- Microtasks

---

## Must-Know Interview Questions

- require() vs import
- module.exports vs exports
- __dirname vs __filename
- process.argv vs process.env
- Purpose of package.json
- Built-in modules (fs, path, os)
- Basic error handling
- Event loop execution order

---

# Mini Projects

## Project 1: Data Table

Goals:

- Fetch Accounts using `@wire`
- Display records
- Add refresh button
- Use imperative Apex

---

## Project 2: Parent Child Communication

Goals:

- Pass values using `@api`
- Send values back using `CustomEvent`
- Handle updates correctly

---

## Project 3: Form + Validation

Goals:

- Input handling
- Field validation
- Conditional rendering
- Error handling