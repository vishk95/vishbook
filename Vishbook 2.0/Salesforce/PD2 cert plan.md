---
title: Salesforce PD2 roadmap
---

# ✅ **Salesforce PD2 – Detailed Syllabus & Topic List**



***



## 🔹 1. Advanced Apex Programming



#### Core Concepts

* Apex class design (scalable, reusable)

* Separation of concerns (Controller–Service–DAO pattern)

* Custom metadata / custom settings usage



#### Triggers & Frameworks

* Trigger design patterns:

  * Single trigger per object

  * Trigger handler framework

* Context variables

* Recursion handling

* Order of execution (deep understanding)



#### Governor Limits & Optimization

* Query optimization techniques

* Avoiding SOQL/DML in loops

* Collections (Map, Set, List) usage

* Heap size and CPU limits tuning



#### Exception Handling

* Custom exceptions

* Try-catch patterns

* Graceful error logging strategies



***



## 🔹 2. Asynchronous Apex (VERY IMPORTANT for PD2)



#### Types

* Future methods

* Queueable Apex

* Batch Apex

* Scheduled Apex



#### Advanced Concepts

* Chaining Queueables

* Batch Apex:

  * Start, Execute, Finish methods

  * Stateful vs Stateless

* Handling large datasets (millions of records)

* Parallel vs serial execution behavior



#### Monitoring & Debugging

* Async jobs monitoring

* Debug logs analysis



***



## 🔹 3. Data Management & Performance



#### Data Handling

* Bulk data processing patterns

* Upsert, Merge operations

* Data skew:

  * Ownership skew

  * Lookup skew



#### Query Design

* Selectivity & indexing

* Query Plan Tool usage

* SOSL vs SOQL use cases



#### Performance Optimization

* Efficient query filtering

* Avoiding locks and contention

* Record locking behavior



***



## 🔹 4. Integration & APIs



(*This is highly important for your profile*)



#### Callouts

* REST and SOAP integrations

* HTTP classes (HttpRequest, HttpResponse)

* Named Credentials

* External services



#### Data Formats

* JSON serialization/deserialization

* XML parsing



#### Advanced Integration Patterns

* Retry mechanism design

* Circuit breaker pattern

* Idempotency in integrations



#### Security in Integration

* OAuth 2.0 flows

* Authentication vs Authorization

* Handling secrets securely



***



## 🔹 5. Testing & Debugging Strategy



#### Test Class Design

* Test data creation strategies:

  * Test.loadData

  * Factory pattern

* @testSetup usage



#### Coverage & Best Practices

* Achieving meaningful coverage (>75% is basic; PD2 expects quality)

* Testing bulk scenarios

* Testing negative cases



#### Mocking & Callouts

* HttpCalloutMock

* Stub API



#### Testing Async Code

* Test.startTest() / Test.stopTest()

* Testing Batch, Queueable, Future methods



***



## 🔹 6. User Interface & LWC Considerations



(*Less weight than Apex, but still tested*)



#### LWC + Apex Interaction

* @AuraEnabled methods

* Imperative vs wire service

* Caching strategies



#### Performance

* Lazy loading

* Efficient data retrieval



***



## 🔹 7. Security & Data Access



#### Sharing & Security

* With sharing / Without sharing / Inherited sharing

* Role hierarchy

* Sharing rules



#### Field & Object Security

* CRUD/FLS enforcement in Apex:

  * Schema methods

  * stripInaccessible()



#### Secure Coding Practices

* Avoiding SOQL Injection

* Proper input validation



***



## 🔹 8. Design Patterns (HIGH IMPORTANCE)



#### Common Patterns

* Trigger framework pattern

* Service layer pattern

* Factory pattern

* Singleton pattern

* Strategy pattern



#### Enterprise Design Principles

* Loose coupling

* High cohesion

* Dependency injection basics



***



## 🔹 9. Transaction Control



#### Concepts

* Savepoints & Rollbacks

* Partial success handling



#### Advanced Behavior

* Mixed DML operations

* Transaction boundaries in async vs sync



***



## 🔹 10. Error Handling & Logging



#### Logging Approaches

* Custom log objects

* Platform Events for logging



#### Fault Tolerance

* Graceful degradation

* Handling integration failures



***



## 🔹 11. Platform Events & Event-Driven Architecture



#### Basics

* Publishing platform events

* Subscribing using triggers



#### Use Cases

* Asynchronous processing

* Integration decoupling



***



## 🔹 12. Salesforce Limits & Architecture



#### Understanding Limits

* Per-transaction limits

* Platform limits vs Apex limits



#### Architecture Design

* Scalability design

* Multi-tenant awareness



***



## 🔹 13. Packaging & Deployment



#### Deployment Concepts

* Change Sets vs SFDX

* Metadata API basics



#### Packaging

* Unlocked packages

* Managed packages (basic understanding)



***



## 🔹 14. Programming Assignment Expectations



This is where many fail. It tests practical skills:



#### You must be able to:

* Implement end-to-end business logic

* Write:

  * Apex classes

  * Triggers

  * Test classes

* Follow:

  * Bulkification

  * Error handling

  * Proper design patterns

* Handle:

  * Large data volumes

  * Edge cases



***



## ✅ **How PD2 Differs from PD1 (Important Insight)**



| Area      | PD1                | PD2                  |

| --------- | ------------------ | -------------------- |

| Depth     | Basic–Intermediate | Advanced             |

| Focus     | Syntax             | Real-world design    |

| Coding    | Limited            | Extensive            |

| Scenarios | Simple             | Complex architecture |



***



## ✅ **High-Weight Topics (Focus More)**



Based on exam pattern + real feedback:

🔥 MUST MASTER:

* Asynchronous Apex (Batch + Queueable)

* Governor limits optimization

* Integration patterns

* Advanced test class design

* Trigger frameworks

* Security implementation



***



## ✅ **Quick Practical Checklist (Use for Revision)**



Before exam, ensure you can:

✔ Design a scalable trigger framework  

✔ Optimize SOQL for large data  

✔ Write batch job handling millions of records  

✔ Mock REST API callouts in test class  

✔ Implement retry logic in integrations  

✔ Handle record locking issues  

✔ Enforce CRUD/FLS in Apex  

✔ Use platform events for async processing



***



If you want next, I can:

✅ Create a **weekly PD2 preparation roadmap tailored to your Compass + API integration work**  

✅ Provide **sample coding assignment (real PD2-style)**  

✅ Share **tricky scenario-based questions like actual exam**
