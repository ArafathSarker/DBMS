# Database Normalization & Anomaly Types

## 📌 What is Normalization?
**Normalization** is a database design technique used to organize data efficiently.  
Its main goals are to:
- Reduce data redundancy
- Improve data integrity
- Avoid anomalies during database operations

Normalization divides large tables into smaller, related tables and defines relationships between them using keys.

---

## 📚 Why Normalization is Important
Without normalization, databases can:
- Store duplicate data
- Become hard to maintain
- Produce incorrect or inconsistent results

Normalization helps keep data **accurate, consistent, and scalable**.

---

## ⚠️ Anomalies in Databases
An **anomaly** is a problem that occurs in a poorly designed database.  
There are **three main types of anomalies**:

---

## 🧨 Types of Anomalies with Examples

| Anomaly Type | Description | Example | Impact |
|-------------|------------|---------|--------|
| **Insertion Anomaly** | Difficulty inserting new data without adding unnecessary data | Cannot add a new course unless at least one student enrolls in it | Leads to missing or incomplete data |
| **Update Anomaly** | Same data stored in multiple places must be updated everywhere | Updating a teacher’s name in multiple rows | Causes data inconsistency |
| **Deletion Anomaly** | Deleting data unintentionally removes important information | Deleting the last student of a course removes course details | Loss of important data |

---

## 🧩 Example (Unnormalized Table)

| StudentID | StudentName | Course | Instructor |
|----------|-------------|--------|------------|
| 1 | Alex | Math | Mr. Smith |
| 2 | Jamie | Math | Mr. Smith |
| 3 | Alex | Science | Ms. Lee |

### Problems:
- Instructor name is repeated
- Updating instructor requires multiple changes
- Deleting a student may delete course info

---

## ✅ Solution: Normalization
By normalizing the table into:
- **Students**
- **Courses**
- **Instructors**
- **Enrollments**

We eliminate redundancy and prevent anomalies.

---

## 🏁 Conclusion
Normalization is essential for:
- Reliable databases
- Accurate data operations
- Avoiding insertion, update, and deletion anomalies

A well-normalized database improves performance, integrity, and maintainability.

---

## 📖 References
- Database Management Systems
- SQL & Relational Database Concepts
