# Third Normal Form (3NF) in DBMS

## Introduction
Third Normal Form (3NF) is an advanced stage of database normalization that focuses on eliminating **transitive functional dependency**. It builds on Second Normal Form (2NF) to further reduce redundancy and improve data integrity.

---

## Definition of 3NF
A relation is said to be in **Third Normal Form (3NF)** if:
- It is already in **Second Normal Form (2NF)**
- It has **no transitive functional dependency**
- Every non-prime attribute is directly dependent on the **primary key**, not on another non-prime attribute

---

## What is Transitive Dependency?
A **transitive dependency** occurs when:
- A non-prime attribute depends on another non-prime attribute
- Instead of depending directly on the primary key

Formally:
X → Y  
Y → Z  

Then:
X → Z  

Where X is a primary key and Y, Z are non-prime attributes.

---

## Example of Table NOT in 3NF

### STUDENT table (In 2NF but NOT in 3NF)

| StudentID | StudentName | DepartmentID | DepartmentName |
|----------|-------------|--------------|----------------|
| 101      | Alex        | D01          | CSE            |
| 102      | Sam         | D02          | ECE            |

Primary Key:
StudentID

Functional Dependencies:
StudentID → StudentName, DepartmentID  
DepartmentID → DepartmentName  

❌ DepartmentName depends on DepartmentID  
❌ Transitive dependency exists  
➡ Table is not in 3NF

---

## Converting Table into 3NF

### STUDENT table

| StudentID | StudentName | DepartmentID |
|----------|-------------|--------------|
| 101      | Alex        | D01          |
| 102      | Sam         | D02          |

Functional Dependency:
StudentID → StudentName, DepartmentID

---

### DEPARTMENT table

| DepartmentID | DepartmentName |
|-------------|----------------|
| D01         | CSE            |
| D02         | ECE            |

Functional Dependency:
DepartmentID → DepartmentName

✔ No transitive dependency  
✔ Tables are in **Third Normal Form (3NF)**

---

## SQL Example

```sql
CREATE TABLE Department (
    DepartmentID VARCHAR(10) PRIMARY KEY,
    DepartmentName VARCHAR(50)
);

CREATE TABLE Student (
    StudentID INT PRIMARY KEY,
    StudentName VARCHAR(50),
    DepartmentID VARCHAR(10)
);
```
## Advantages of Third Normal Form (3NF)

- Eliminates transitive dependencies  
- Reduces data redundancy further  
- Improves data integrity  
- Makes database maintenance easier  

---

## Limitations of Third Normal Form (3NF)

- May increase the number of tables  
- Requires joins for data retrieval  
- Slightly complex database design  

---

## Difference Between 2NF and 3NF

| Aspect | 2NF | 3NF |
|------|-----|-----|
| Dependency removed | Partial | Transitive |
| Based on | 1NF | 2NF |
| Data redundancy | Reduced | Further reduced |
