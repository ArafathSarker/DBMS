# DBMS Architecture Levels

This repository contains explanations and illustrations of different **Database Management System (DBMS) architectures**, including **One-Level, Two-Level, and Tree-Level Architectures**.

---

## Table of Contents

- [One-Level Architecture](#one-level-architecture)  
- [Two-Level Architecture](#two-level-architecture)  
- [Tree-Level Architecture](#tree-level-architecture)  
- [References](#references)  

---

## One-Level Architecture

The **One-Level Architecture** of DBMS is the simplest architecture where the database system consists of only **one level**.  

### Features:
- Only **one layer** is present in the system.
- Users directly interact with the database without any abstraction.
- Suitable for **small databases** or simple applications.
  
### Diagram:
| Order | Component |
|-------|-----------|
| 1     | **User**  |
| ↓     |           |
| 2     | **Database** |



---

## Two-Level Architecture

The **Two-Level Architecture** introduces **abstraction** between the user and the physical database.  
It is also known as the **Schema Architecture**.  

### Levels:
1. **External Level (View Level)**  
   - Represents the user's view of the database.
   - Multiple external schemas can exist for different users.
2. **Internal Level (Storage Level)**  
   - Handles the physical storage of data.
   - Manages data structures, file organizations, and indexes.

### Features:
- Provides **data abstraction**.
- Users don’t need to know how data is stored physically.
- Enhances security and reduces complexity.

### Diagram:

| Order | DBMS Level                     | Component   |
|-------|--------------------------------|-------------|
| 1     | **External View**              | User        |
| ↓     |                                |             |
| 2     | **Conceptual Schema**          | DBMS Engine |
| ↓     |                                |             |
| 3     | **Internal Schema (Storage)**  | Database    |




---

## Tree-Level Architecture (Three-Level Architecture)

The **Tree-Level Architecture** is the **standard architecture** used in modern DBMS.  
It provides **complete data abstraction** and separates the database into three levels:

### Levels:
1. **External Level (User View)**  
   - Individual user views of the database.
2. **Conceptual Level (Logical Level)**  
   - Represents the logical structure of the entire database.
   - Hides physical storage details.
3. **Internal Level (Physical Level)**  
   - Describes how data is physically stored in the database.

### Features:
- Supports **data independence** (both logical and physical).
- Ensures better **security and consistency**.
- Used in **most modern relational DBMS**.

### Diagram:

 | Order | DBMS Level          | Component        |
|-------|--------------------|------------------|
| 1     | **External Level**  | User 1, User 2   |
| ↓     |                    |                  |
| 2     | **Conceptual Level** | Logical Schema |
| ↓     |                    |                  |
| 3     | **Internal Level**  | Physical Data   |



---

## References

1. Abraham Silberschatz, Henry F. Korth, S. Sudarshan - *Database System Concepts*  
2. Ramakrishnan, Gehrke - *Database Management Systems*  
3. https://www.geeksforgeeks.org/dbms-architecture/

---

*This README is prepared for educational purposes to explain DBMS architectures.*
