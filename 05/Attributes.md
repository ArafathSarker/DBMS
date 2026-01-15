# Attributes in DBMS

This document explains the concept of **Attributes in Database Management Systems (DBMS)** and the different **types of attributes** used in database design.

---

## Table of Contents

- [Introduction to Attributes](#introduction-to-attributes)
- [Types of Attributes](#types-of-attributes)
  - [Simple Attribute](#simple-attribute)
  - [Composite Attribute](#composite-attribute)
  - [Single-Valued Attribute](#single-valued-attribute)
  - [Multi-Valued Attribute](#multi-valued-attribute)
  - [Derived Attribute](#derived-attribute)
  - [Key Attribute](#key-attribute)
- [Comparison Table](#comparison-table)
- [Importance of Attributes](#importance-of-attributes)
- [Conclusion](#conclusion)
- [References](#references)

---

## Introduction to Attributes

An **Attribute** is a property or characteristic that describes an **entity** in a database.

### Example:
- Entity: **Student**
- Attributes: Student_ID, Name, Age, Address

Attributes store the actual data values in a database.

---

## Types of Attributes

Attributes in DBMS are classified into several types based on their nature and usage.

---

## Simple Attribute

A **Simple Attribute** cannot be divided into smaller parts.

### Example:
- Age
- Gender
- Salary

---

## Composite Attribute

A **Composite Attribute** can be divided into **sub-attributes**.

### Example:
- Name → First_Name, Last_Name
- Address → Street, City, State, PIN

---

## Single-Valued Attribute

A **Single-Valued Attribute** holds **only one value** for an entity.

### Example:
- Date_of_Birth
- Roll_Number

---

## Multi-Valued Attribute

A **Multi-Valued Attribute** can store **multiple values** for a single entity.

### Example:
- Phone_Numbers
- Email_Addresses

---

## Derived Attribute

A **Derived Attribute** is an attribute whose value is **calculated from other attributes**.

### Example:
- Age (derived from Date_of_Birth)
- Total_Price (derived from Quantity × Price)

---

## Key Attribute

A **Key Attribute** is used to **uniquely identify** an entity.

### Example:
- Student_ID
- Employee_ID

Key attributes play an important role in maintaining **entity integrity**.

---

## Comparison Table

```markdown
| Attribute Type      | Description                              | Example                  |
|---------------------|------------------------------------------|--------------------------|
| Simple              | Cannot be subdivided                     | Age                      |
| Composite           | Can be divided into sub-attributes       | Address                  |
| Single-Valued       | Holds only one value                     | Roll_Number              |
| Multi-Valued        | Holds multiple values                    | Phone_Numbers            |
| Derived             | Computed from other attributes           | Age from DOB             |
| Key                 | Uniquely identifies an entity            | Student_ID               |
