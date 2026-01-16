# Functional Dependency in DBMS

## Introduction
In Database Management Systems (DBMS), a Functional Dependency (FD) is a constraint that defines the relationship between attributes in a relational database. Functional dependencies are used to maintain data consistency and are the foundation of database normalization.

They help in:
- Reducing data redundancy
- Eliminating update, insertion, and deletion anomalies
- Designing efficient and well-structured databases
- Identifying candidate keys and primary keys

---

## Definition of Functional Dependency
A functional dependency is denoted as:

X → Y

This means that the value of attribute set X uniquely determines the value of attribute set Y.

If two tuples have the same value of X, they must have the same value of Y.

---

## Example
Consider the STUDENT table:

| StudentID | Name | Department |
|----------|------|------------|
| 101      | Alex | CSE        |
| 102      | Sam  | ECE        |

Functional Dependency:
StudentID → Name, Department

Here, StudentID uniquely identifies Name and Department.

---

## Types of Functional Dependency

---

## 1. Trivial Functional Dependency
A functional dependency is said to be trivial if the right-hand side (RHS) is a subset of the left-hand side (LHS).

Definition:
X → Y, where Y ⊆ X

Example:
{StudentID, Name} → Name

Trivial functional dependencies are always true and do not provide any new information.

---

## 2. Non-Trivial Functional Dependency
A functional dependency is non-trivial if the right-hand side is not a subset of the left-hand side.

Definition:
X → Y, where Y ⊄ X

Example:
StudentID → Name

---

## 3. Completely Non-Trivial Functional Dependency
A functional dependency is completely non-trivial if the left-hand side and right-hand side have no attributes in common.

Example:
StudentID → Department

---

## 4. Partial Functional Dependency
A partial functional dependency occurs when a non-prime attribute is functionally dependent on only a part of a composite primary key.

Example:
Primary Key: (StudentID, CourseID)

Functional Dependency:
StudentID → StudentName

This violates Second Normal Form (2NF).

---

## 5. Full Functional Dependency
A functional dependency is full if the dependent attribute depends on the entire composite key and not on any part of it.

Example:
(StudentID, CourseID) → Grade

If any attribute is removed from the left-hand side, the dependency no longer holds.

---

## 6. Transitive Functional Dependency
A transitive dependency occurs when one non-key attribute depends on another non-key attribute.

Condition:
X → Y  
Y → Z  

Then:
X → Z

Example:
StudentID → DepartmentID  
DepartmentID → DepartmentName  

So:
StudentID → DepartmentName

This violates Third Normal Form (3NF).

---

## Diagram Representation (ASCII)

StudentID  
↓  
DepartmentID  
↓  
DepartmentName  

---

## SQL Example

```sql
CREATE TABLE Student (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(50),
    DepartmentID INT,
    DepartmentName VARCHAR(50)
);
