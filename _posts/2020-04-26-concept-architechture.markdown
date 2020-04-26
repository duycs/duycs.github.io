---
layout: post
title: Architecture Concept
description: Concept, design and implement some architecture
date: 2020-04-26 10:59:00 +0700
categories: demo
thumbnail: https://lh3.googleusercontent.com/xxnvZQEUycvQG3rfj1NzWlEba-6FamXuL3TftTgWgqJwWSChsptxsxLiZycEALSQu4YsVDWlFV_-Cvd45SSl_EU8iGwWvEPrQ8JfG73WqLiDJUE2W9cfQkXLAe1u46S87aj-2uNOYrb3WpyUApOm3AKZDEVnB1f9iJS4F63b5cu1Bc7rGfLGymzITPINR33ck4GqODAyiFS9_8opRJhPbqHLSc5bvs46HdOcOwvuRmEv29xKzJbsOvz3ISuLRhmMqio35NyJttBgHCOTRAIFoDUfd2jLewUHo5E2B-7NAksEc854VmUwzKZIgrCoPWWOg8AtvMXcBB8hlLudJfhNe90MhkAvxxDIifPAownkyp_347dI5ZFqeL4WJhSfIELaLFYPkNw8MBDymq7YuyaTNEUc5S_PZF9tma008Wh141qWzNJ_xTH-htBSLXhluGUgdPNFzB7eQqYVJbtxDNjtX8V44muRswYvUaLBMz_uyIxT1xiRGN1QlL0Dol5IVCUOM2rqzYh-tqpSlQ9434yf82vbUgMhleqe5YLD3lJ28GJnrdLBBeMjT6uKrYc1Oi-fI2Bc44XyuCAkpEiZQrI8tsoefrOB43RyRP8yJeAFxt53pPTbCOdHq9R3Mnt94EWSUlfeFTcUxH5SinhNGXu7lTYNVhHLg9tgiyiYxQPNMOhaHVnaFIE3r7HBzi6s49NvNyk5WT44I_EaCGc4-uH3Mxm5hRLpmDihbA2vLBM9RaUlDUMdv_-RUaY=w1472-h1060-no
---

![](https://lh3.googleusercontent.com/xxnvZQEUycvQG3rfj1NzWlEba-6FamXuL3TftTgWgqJwWSChsptxsxLiZycEALSQu4YsVDWlFV_-Cvd45SSl_EU8iGwWvEPrQ8JfG73WqLiDJUE2W9cfQkXLAe1u46S87aj-2uNOYrb3WpyUApOm3AKZDEVnB1f9iJS4F63b5cu1Bc7rGfLGymzITPINR33ck4GqODAyiFS9_8opRJhPbqHLSc5bvs46HdOcOwvuRmEv29xKzJbsOvz3ISuLRhmMqio35NyJttBgHCOTRAIFoDUfd2jLewUHo5E2B-7NAksEc854VmUwzKZIgrCoPWWOg8AtvMXcBB8hlLudJfhNe90MhkAvxxDIifPAownkyp_347dI5ZFqeL4WJhSfIELaLFYPkNw8MBDymq7YuyaTNEUc5S_PZF9tma008Wh141qWzNJ_xTH-htBSLXhluGUgdPNFzB7eQqYVJbtxDNjtX8V44muRswYvUaLBMz_uyIxT1xiRGN1QlL0Dol5IVCUOM2rqzYh-tqpSlQ9434yf82vbUgMhleqe5YLD3lJ28GJnrdLBBeMjT6uKrYc1Oi-fI2Bc44XyuCAkpEiZQrI8tsoefrOB43RyRP8yJeAFxt53pPTbCOdHq9R3Mnt94EWSUlfeFTcUxH5SinhNGXu7lTYNVhHLg9tgiyiYxQPNMOhaHVnaFIE3r7HBzi6s49NvNyk5WT44I_EaCGc4-uH3Mxm5hRLpmDihbA2vLBM9RaUlDUMdv_-RUaY=w1472-h1060-no)

### Criteria
Concept, design and implement some architecture

### Keyword
- Clean Architecture
- Onion Architecture
- Dependence Injection
- 

### 1. Dependence Injection
#### Criteria
- 
- 

At the Onion Architecture, Jeffrey Palermo describe about Independent in software design:
"The Onion Architecture relies heavily on the Dependency Inversion principle.  The application core needs implementation of core interfaces, and if those implementing classes reside at the edges of the application, we need some mechanism for injecting that code at runtime so the application can do something useful."

#### 1.1 Dependency Inversion principle
In object-oriented design, the dependency inversion principle is a specific form of decoupling software modules.


### Why?
- At the Clean Architecture of Uncle-Bob, He describle about Independent in software design:
"
That each of these architecture produrce system that are:
1. Independent of Frameworks. The architecture does not depend on the existence of some library of feature laden software. This allows you to use such frameworks as tools, rather than having to cram your system into their limited constraints.

2. Testable. The business rules can be tested without the UI, Database, Web Server, or any other external element.

3. Independent of UI. The UI can change easily, without changing the rest of the system. A Web UI could be replaced with a console UI, for example, without changing the business rules.

4. Independent of Database. You can swap out Oracle or SQL Server, for Mongo, BigTable, CouchDB, or something else. Your business rules are not bound to the database.

5. Independent of any external agency. In fact your business rules simply don’t know anything at all about the outside world.
"


### 2. Provider

### 3. Adapter

### 4. Observer


### 

---
### References
- https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html
- https://jeffreypalermo.com/2008/07/the-onion-architecture-part-2/
- https://en.wikipedia.org/wiki/Dependency_inversion_principle
