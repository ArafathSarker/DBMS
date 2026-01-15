# Entity in DBMS

This document explains the concept of an **Entity in Database Management Systems (DBMS)** and the different **types of entities** used in database design.

---

## Table of Contents

- [Introduction to Entity](#introduction-to-entity)
- [Types of Entities](#types-of-entities)
  - [Strong Entity](#strong-entity)
  - [Weak Entity](#weak-entity)
- [Comparison Between Strong and Weak Entity](#comparison-between-strong-and-weak-entity)
- [Importance of Entities in DBMS](#importance-of-entities-in-dbms)
- [Conclusion](#conclusion)
- [References](#references)

---

## Introduction to Entity

An **Entity** is a real-world object or concept that can be **uniquely identified** and about which data is stored in a database.

### Examples:
- Student
- Employee
- Course
- Department

Each entity is represented by a **set of attributes** that describe its properties.

---

## Types of Entities

Entities in DBMS are mainly classified into **two types**:

---

## Strong Entity

A **Strong Entity** is an entity that:
- Has its **own primary key**
- Exists **independently** of other entities

### Characteristics:
- Primary key uniquely identifies each record
- Does not depend on another entity
- Represented by a **single rectangle** in ER diagrams

### Example:
- **Student** (Student_ID, Name, Age)
- **Employee** (Emp_ID, Name, Salary)

---

## Weak Entity

A **Weak Entity** is an entity that:
- **Does not have a primary key**
- Depends on a **strong entity** for identification

It is identified using:
- A **partial key**
- The primary key of the related strong entity

### Characteristics:
- Cannot exist independently
- Depends on a strong entity
- Represented by a **double rectangle** in ER diagrams

### Example:
- **Dependent** (Dependent_Name, Relationship) depends on Employee
- **Order_Items** depends on Order

---

## Comparison Between Strong and Weak Entity

```markdown
| Feature              | Strong Entity              | Weak Entity                    |
|----------------------|----------------------------|--------------------------------|
| Primary Key          | Present                    | Not present                    |
| Dependency           | Independent                | Depends on strong entity       |
| Identification       | By its own key             | Partial key + strong entity key|
| ER Diagram Symbol    | Single Rectangle           | Double Rectangle               |
| Example              | Student, Employee          | Dependent, Order_Items         |
