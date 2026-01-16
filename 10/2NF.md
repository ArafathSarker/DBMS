# Second Normal Form (2NF) in DBMS

## Introduction
Second Normal Form (2NF) is the next step after First Normal Form (1NF) in database normalization. It focuses on removing **partial functional dependency** to reduce data redundancy and improve data integrity.

---

## Definition of 2NF
A relation is in **Second Normal Form (2NF)** if:
- It is already in **First Normal Form (1NF)**
- It has **no partial functional dependency**
- Every non-prime attribute is fully functionally dependent on the **entire primary key**

---

## What is Partial Functional Dependency?
A **partial dependency** occurs when a non-prime attribute depends on **only a part of a composite primary key** instead of the whole key.

---

## Example of Table NOT in 2NF

### ENROLLMENT table (In 1NF but NOT in 2NF)

| StudentID | CourseID | StudentName | CourseName |
|----------|----------|-------------|------------|
| 101      | C101     | Alex        | DBMS       |
| 101      | C102     | Alex        | OS         |
| 102      | C101     | Sam         | DBMS       |

Primary Key:
(StudentID, CourseID)

Functional Dependencies:
StudentID → StudentName  
CourseID → CourseName  

❌ StudentName depends only on StudentID  
❌ CourseName depends only on CourseID  
➡ Partial dependency exists

---

## Converting Table into 2NF

### STUDENT table

| StudentID | StudentName |
|----------|-------------|
| 101      | Alex        |
| 102      | Sam         |

Functional Dependency:
StudentID → StudentName

---

### COURSE table

| CourseID | CourseName |
|----------|------------|
| C101     | DBMS       |
| C102     | OS         |

Functional Dependency:
CourseID → CourseName

---

### ENROLLMENT table

| StudentID | CourseID |
|----------|----------|
| 101      | C101     |
| 101      | C102     |
| 102      | C101     |

Functional Dependency:
(StudentID, CourseID) → (StudentID, CourseID)

✔ No partial dependency  
✔ Tables are in **Second Normal Form**

---

## SQL Example

```sql
CREATE TABLE Student (
    StudentID INT PRIMARY KEY,
    StudentName VARCHAR(50)
);

CREATE TABLE Course (
    CourseID VARCHAR(10) PRIMARY KEY,
    CourseName VARCHAR(50)
);

CREATE TABLE Enrollment (
    StudentID INT,
    CourseID VARCHAR(10),
    PRIMARY KEY (StudentID, CourseID)
);
```

## Advantages of Second Normal Form (2NF)

- Removes partial functional dependency  
- Reduces data redundancy  
- Improves data consistency  
- Makes database design cleaner and more structured  

---

## Limitations of Second Normal Form (2NF)

- Transitive dependencies may still exist  
- Not sufficient for complete normalization  

## Difference Between First Normal Form (1NF) and Second Normal Form (2NF)

| Aspect | 1NF | 2NF |
|------|-----|-----|
| Focus | Atomic values | Full dependency |
| Dependency handled | Repeating groups | Partial dependency |
| Composite key issue | Not addressed | Addressed |
