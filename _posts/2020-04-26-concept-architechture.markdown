---
layout: post
title: Architecture Concept
description: Concept, design and implement some architecture
date: 2020-04-26 10:59:00 +0700
categories: demo
thumbnail: https://lh3.googleusercontent.com/x8BP39OaN9oGOL7t6Ys6waW4MfDJKf1ZhzLG150OKFnqMg2Q-Yc2IjVruzOlkjCnudJV4e3Md88w00OPORHB6qLUcxzSk6jP9pkBfPN1enCyLP5RQUGGT6AJR58FA6cCka2sgrZ21jzL39MUAcCs2ih6PStYqThmvr2FpcxRHzWW0yKXKRRg8MVzuQQUCuRiBFx3BkVSrnYOKIlI4OUaE91ZhgKhd0zKluoXtnOs7DJG18tZqVJ4Ja1gF7hcM7at3DCPKBHjNIkAzpuIOrYOHqL1Fghulnv8OMy4VS0M4COz0nxVhQmg4A6z3yR4zGG2If6engrqnpmqP5H4ytiHSI00Tsbu-jUEL8tyzg6IeOS6O9-fJZ3k1uesCkqaW2PFthM3Y9AfQC5_8XRq_ca6B3d2FcBXOvw14fWWtEh_sqK84CyLHZ3gzRSq7FLfDCritN2RR_81jmz5YWMmiq_bT9OMg5iNECxGOvGyicizZ0W3DRW0bz5bDT42vQwztOCek3uYNovE3DDET_vTFGfkcVKl2bENe4Ua1M0grZgPdnKXe8fFG5b6bzt0PZ-2X5kp_oPwOBxzwZ48wQksxb7knLxfDBTLkRtCFjrUdedHTFGED4Y_dClwpcSqC225YrJW5XT8wdEbTxXEcnC3AjRHXMubjUPiJmNcbCrdkrHfbso0webDiEHmLbFpIXKV4gmpgkjjYRH7SfrYm96HuSESH3ShelllCa6PfQmnXipm_BRQxpNTRc0K8ls=w998-h688-no
---

![](https://lh3.googleusercontent.com/x8BP39OaN9oGOL7t6Ys6waW4MfDJKf1ZhzLG150OKFnqMg2Q-Yc2IjVruzOlkjCnudJV4e3Md88w00OPORHB6qLUcxzSk6jP9pkBfPN1enCyLP5RQUGGT6AJR58FA6cCka2sgrZ21jzL39MUAcCs2ih6PStYqThmvr2FpcxRHzWW0yKXKRRg8MVzuQQUCuRiBFx3BkVSrnYOKIlI4OUaE91ZhgKhd0zKluoXtnOs7DJG18tZqVJ4Ja1gF7hcM7at3DCPKBHjNIkAzpuIOrYOHqL1Fghulnv8OMy4VS0M4COz0nxVhQmg4A6z3yR4zGG2If6engrqnpmqP5H4ytiHSI00Tsbu-jUEL8tyzg6IeOS6O9-fJZ3k1uesCkqaW2PFthM3Y9AfQC5_8XRq_ca6B3d2FcBXOvw14fWWtEh_sqK84CyLHZ3gzRSq7FLfDCritN2RR_81jmz5YWMmiq_bT9OMg5iNECxGOvGyicizZ0W3DRW0bz5bDT42vQwztOCek3uYNovE3DDET_vTFGfkcVKl2bENe4Ua1M0grZgPdnKXe8fFG5b6bzt0PZ-2X5kp_oPwOBxzwZ48wQksxb7knLxfDBTLkRtCFjrUdedHTFGED4Y_dClwpcSqC225YrJW5XT8wdEbTxXEcnC3AjRHXMubjUPiJmNcbCrdkrHfbso0webDiEHmLbFpIXKV4gmpgkjjYRH7SfrYm96HuSESH3ShelllCa6PfQmnXipm_BRQxpNTRc0K8ls=w998-h688-no)

### Criteria
Concept, design and implement some architecture

### Keyword
- Clean Architecture
- Onion Architecture
- Dependence Injection

### SOLID Concepts
#### Single responsibility principle
A class should only have a single responsibility, that is, only changes to one part of the software's specification should be able to affect the specification of the class.

#### Open–closed principle
"Software entities ... should be open for extension, but closed for modification."

#### Liskov substitution principle
"Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program." See also design by contract.

#### Interface segregation principle
"Many client-specific interfaces are better than one general-purpose interface."

#### Dependency inversion principle
One should "depend upon abstractions, [not] concretions."



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

### Aggregate Model
- Entity, Root Entity
- Value Object
- Enumration

### Events
- Domain Event
- Intergration Event

### Cross cuting concern
- Business rules
- Caching
- Logging
- Data validation
- Environment variables
- Error detection and correction
- Internationalization and localization, ex language localization
- Security
- Memory management
- Monitotring
- Transaction persistence
- Synchronization
- Dependency injection

### 

---
### References
- https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html
- https://jeffreypalermo.com/2008/07/the-onion-architecture-part-2/
- https://en.wikipedia.org/wiki/Dependency_inversion_principle
