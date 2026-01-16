# Data Redundancy Types: Row-Level & Column-Level

## 📌 What is Data Redundancy?
**Data redundancy** occurs when the same data is stored multiple times unnecessarily in a database.  
This leads to:
- Wasted storage
- Data inconsistency
- Update, insertion, and deletion anomalies

Understanding redundancy helps design better and normalized databases.

---

## 🔁 Types of Data Redundancy

Data redundancy can mainly be classified into:
1. **Row-Level Redundancy**
2. **Column-Level Redundancy**

---

## 🧱 Row-Level Redundancy

### 🔍 What is Row-Level Redundancy?
Row-level redundancy occurs when **entire rows or major parts of rows are duplicated** in a table.

This usually happens when the same entity information is repeated for multiple records.

---

### ❌ Example (Row-Level Redundancy)

| StudentID | StudentName | Course | Instructor |
|----------|------------|--------|------------|
| 1 | Alex | Math | Mr. Smith |
| 1 | Alex | Science | Ms. Lee |

### 🚨 Redundancy Issue
- Student information (`StudentID`, `StudentName`) is repeated
- If the student's name changes, it must be updated in multiple rows

---

### ⚠️ Impact
- **Update Anomaly**: Multiple updates needed for the same data
- **Increased storage usage**
- **Risk of inconsistent data**

---

### ✅ Solution
Split data into separate tables:
- Students
- Courses
- Enrollments

---

## 🧩 Column-Level Redundancy

### 🔍 What is Column-Level Redundancy?
Column-level redundancy occurs when **unnecessary or derived columns** are stored in a table.

These columns can be calculated from other columns but are stored repeatedly.

---

### ❌ Example (Column-Level Redundancy)

| OrderID | Product | UnitPrice | Quantity | TotalPrice |
|--------|---------|-----------|----------|------------|
| 101 | Laptop | 500 | 2 | 1000 |
| 102 | Mouse | 20 | 3 | 60 |

### 🚨 Redundancy Issue
- `TotalPrice` is derived from `UnitPrice × Quantity`
- If `UnitPrice` changes, `TotalPrice` must also be updated

---

### ⚠️ Impact
- **Update Anomaly**
- Possibility of incorrect totals
- Unnecessary storage usage

---

### ✅ Solution
Remove derived columns and calculate them when needed.

---

## 📊 Comparison Table

| Feature | Row-Level Redundancy | Column-Level Redundancy |
|-------|---------------------|------------------------|
| Occurs In | Multiple rows | Multiple columns |
| Type of Duplication | Entire records or attributes | Derived or dependent columns |
| Common Cause | Poor table design | Storing calculated data |
| Main Risk | Data inconsistency | Incorrect updates |
| Fixed By | Table decomposition | Removing derived columns |

---

## 🏁 Conclusion
- **Row-level redundancy** duplicates data across rows
- **Column-level redundancy** stores unnecessary columns
- Both increase anomalies and reduce database reliability
- Proper normalization minimizes both redundancy types

---

## 📖 References
- Database Management Systems
- Relational Database Design Principles
