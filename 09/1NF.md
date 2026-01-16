# First Normal Form (1NF) in DBMS

## Introduction
First Normal Form (1NF) is the first step in the process of database normalization. A relation is said to be in **First Normal Form (1NF)** if it ensures that the table structure is simple, clear, and free from repeating or multi-valued attributes.

---

## Definition of 1NF
A table is in **First Normal Form (1NF)** if:
- Each attribute contains **atomic (indivisible) values**
- There are **no repeating groups or multi-valued attributes**
- Each record can be uniquely identified

---

## Rules of First Normal Form
To satisfy 1NF, a table must follow these rules:
1. Each field should contain a single value
2. Each column should have a unique name
3. Values in a column must be of the same domain
4. Each row should be uniquely identifiable (using a primary key)

---

## Example of Table NOT in 1NF

### STUDENT table (Not in 1NF)

| StudentID | Name | Subjects        |
|----------|------|-----------------|
| 101      | Alex | Math, Physics   |
| 102      | Sam  | Chemistry       |

❌ The `Subjects` column contains **multiple values**, which violates 1NF.

---

## Converting Table into 1NF

### STUDENT table (In 1NF)

| StudentID | Name | Subject   |
|----------|------|-----------|
| 101      | Alex | Math      |
| 101      | Alex | Physics  |
| 102      | Sam  | Chemistry |

✔ Each field contains a **single atomic value**  
✔ No repeating groups  
✔ Table satisfies **First Normal Form**

---

## Functional Dependency in 1NF

Functional Dependency:
StudentID → Name

Here, `StudentID` uniquely determines the `Name`.

---

## SQL Example

```sql
CREATE TABLE Student (
    StudentID INT,
    Name VARCHAR(50),
    Subject VARCHAR(50),
    PRIMARY KEY (StudentID, Subject)
);
