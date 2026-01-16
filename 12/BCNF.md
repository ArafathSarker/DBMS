# Boyce–Codd Normal Form (BCNF) in DBMS

## Introduction
Boyce–Codd Normal Form (BCNF) is an advanced version of Third Normal Form (3NF). It was introduced to handle certain anomalies that are not resolved by 3NF. BCNF ensures a stronger form of normalization by enforcing stricter rules on functional dependencies.

---

## Definition of BCNF
A relation is in **Boyce–Codd Normal Form (BCNF)** if:
- It is already in **Third Normal Form (3NF)**
- For every functional dependency **X → Y**, **X must be a super key**

In simple words:
> Every determinant must be a candidate key.

---

## Why BCNF is Needed
3NF allows some redundancy in cases where:
- A non-prime attribute determines a prime attribute

BCNF removes these remaining anomalies by enforcing stricter dependency rules.

---

## Example of Table NOT in BCNF

### COURSE table (In 3NF but NOT in BCNF)

| StudentID | Course | Instructor |
|----------|--------|------------|
| 101      | DBMS   | Prof. A    |
| 102      | OS     | Prof. B    |
| 103      | DBMS   | Prof. A    |

Functional Dependencies:
StudentID, Course → Instructor  
Instructor → Course  

Candidate Keys:
(StudentID, Course)  

❌ Instructor is not a super key  
❌ Dependency violates BCNF

---

## Converting Table into BCNF

### INSTRUCTOR table

| Instructor | Course |
|-----------|--------|
| Prof. A   | DBMS   |
| Prof. B   | OS     |

Functional Dependency:
Instructor → Course

---

### STUDENT_COURSE table

| StudentID | Instructor |
|----------|------------|
| 101      | Prof. A    |
| 102      | Prof. B    |
| 103      | Prof. A    |

Functional Dependency:
(StudentID, Instructor) → StudentID, Instructor

✔ All determinants are super keys  
✔ Tables are in **BCNF**

---

## SQL Example

```sql
CREATE TABLE Instructor (
    Instructor VARCHAR(50) PRIMARY KEY,
    Course VARCHAR(50)
);

CREATE TABLE StudentCourse (
    StudentID INT,
    Instructor VARCHAR(50),
    PRIMARY KEY (StudentID, Instructor)
);
```
## Advantages of BCNF

- Removes all functional dependency anomalies  
- Eliminates redundancy more effectively than 3NF  
- Improves data integrity  
- Produces highly normalized tables  

---

## Limitations of BCNF

- May decompose tables excessively  
- Increases number of joins  
- Slightly complex to understand and implement  

---

## Difference Between 3NF and BCNF

| Aspect      | 3NF                  | BCNF                     |
|------------|--------------------|-------------------------|
| Determinant | Can be non-key      | Must be a super key     |
| Strength    | Less strict         | More strict             |
| Redundancy  | Some redundancy allowed | No redundancy       |
