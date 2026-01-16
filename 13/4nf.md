# Fourth Normal Form (4NF) in DBMS

## Introduction
Fourth Normal Form (4NF) is an advanced stage of database normalization that deals with **multi-valued dependencies (MVDs)**. It ensures that no table contains two or more independent multi-valued facts about an entity.

4NF builds on **BCNF** and removes redundancy caused by **multi-valued dependencies**.

---

## Definition of 4NF
A relation is in **Fourth Normal Form (4NF)** if:
- It is already in **Boyce–Codd Normal Form (BCNF)**
- It has **no multi-valued dependencies (MVDs)**

**Multi-valued dependency (MVD):**  
A multi-valued dependency exists when one attribute in a table uniquely determines another attribute **independently** of other attributes.

---

## Example of Table NOT in 4NF

### STUDENT table (In BCNF but NOT in 4NF)

| StudentID | Hobby    | Language  |
|----------|----------|-----------|
| 101      | Painting | English   |
| 101      | Painting | Spanish   |
| 101      | Music    | English   |
| 101      | Music    | Spanish   |

- StudentID → Hobby (multi-valued)  
- StudentID → Language (multi-valued)  

❌ Hobby and Language are independent of each other  
➡ Multi-valued dependency exists  

---

## Converting Table into 4NF

### STUDENT_HOBBY table

| StudentID | Hobby    |
|----------|----------|
| 101      | Painting |
| 101      | Music    |

### STUDENT_LANGUAGE table

| StudentID | Language |
|----------|----------|
| 101      | English  |
| 101      | Spanish  |

✔ No multi-valued dependency  
✔ Tables are in **Fourth Normal Form (4NF)**

---

## SQL Example

```sql
CREATE TABLE StudentHobby (
    StudentID INT,
    Hobby VARCHAR(50),
    PRIMARY KEY (StudentID, Hobby)
);

CREATE TABLE StudentLanguage (
    StudentID INT,
    Language VARCHAR(50),
    PRIMARY KEY (StudentID, Language)
);
```
## Advantages of Fourth Normal Form (4NF)

- Eliminates multi-valued dependencies  
- Reduces redundancy caused by independent attributes  
- Improves data integrity and consistency  
- Simplifies database maintenance  

---

## Limitations of Fourth Normal Form (4NF)

- May require decomposing tables further  
- Can increase the number of tables and joins  
- Slightly complex to implement and manage  
