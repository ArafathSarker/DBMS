# Integrity Constraints in DBMS

This document explains **Integrity Constraints in Database Management Systems (DBMS)**, their purpose, and different types used to ensure data accuracy and consistency.

---

## Table of Contents

- [Introduction to Integrity Constraints](#introduction-to-integrity-constraints)
- [Types of Integrity Constraints](#types-of-integrity-constraints)
  - [Domain Integrity Constraint](#domain-integrity-constraint)
  - [Entity Integrity Constraint](#entity-integrity-constraint)
  - [Referential Integrity Constraint](#referential-integrity-constraint)
  - [Key Integrity Constraint](#key-integrity-constraint)
- [Importance of Integrity Constraints](#importance-of-integrity-constraints)
- [Conclusion](#conclusion)
- [References](#references)

---

## Introduction to Integrity Constraints

**Integrity Constraints** are a set of rules applied to a database to ensure the **accuracy, consistency, and reliability of data**.

They prevent invalid data from being inserted into the database and help maintain the correctness of relationships between tables.

---

## Types of Integrity Constraints

There are several types of integrity constraints in DBMS:

---

## Domain Integrity Constraint

**Domain Integrity** ensures that the values entered into a column are **valid and within a defined domain**.

### Examples:
- Age must be a positive integer
- Salary should be greater than zero
- Gender must be `Male`, `Female`, or `Other`

### Commonly enforced using:
- Data types
- `CHECK` constraint
- `NOT NULL`

---

## Entity Integrity Constraint

**Entity Integrity** ensures that each table has a **primary key** and that the primary key value is:
- **Unique**
- **Not NULL**

This guarantees that each record can be uniquely identified.

### Example:
- Student ID cannot be NULL or duplicated

---

## Referential Integrity Constraint

**Referential Integrity** ensures that relationships between tables remain consistent.

It requires that:
- A **foreign key** value must either match a primary key in the referenced table
- Or be NULL

### Example:
- A `student_id` in the `Enrollment` table must exist in the `Student` table

### Common actions:
- `ON DELETE CASCADE`
- `ON UPDATE CASCADE`
- `SET NULL`

---

## Key Integrity Constraint

**Key Integrity** ensures that keys uniquely identify records in a table.

### Types of Keys:
- Primary Key
- Candidate Key
- Unique Key

### Rule:
- No two rows can have the same key value

---

## Comparison Table

```markdown
| Constraint Type       | Purpose                               | Example                         |
|-----------------------|----------------------------------------|----------------------------------|
| Domain Integrity      | Validates attribute values             | Age > 0                          |
| Entity Integrity      | Ensures unique primary key             | Student_ID NOT NULL              |
| Referential Integrity | Maintains table relationships          | Foreign Key constraint           |
| Key Integrity         | Ensures uniqueness of keys             | Unique Roll Number               |
