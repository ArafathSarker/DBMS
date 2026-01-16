# Normalization Types: Row-Level & Column-Level Understanding

## 📌 What is Normalization?
Normalization is the process of structuring a database to:
- Reduce data redundancy
- Improve data consistency
- Prevent anomalies (insertion, update, deletion)

Apart from formal normal forms (1NF, 2NF, 3NF), normalization can also be **understood practically** as:
- **Row-Level Normalization**
- **Column-Level Normalization**

These concepts help beginners understand *where* duplication and problems occur.

---

## 🧱 Row-Level Normalization

### 🔍 What is Row-Level Normalization?
Row-level normalization focuses on **removing duplicate rows or repeating groups** in a table.

Each row should represent **one unique record**.

---

### ❌ Before Row-Level Normalization (Problem)

| StudentID | Name | Course1 | Course2 |
|---------|------|---------|---------|
| 1 | Alex | Math | Science |
| 2 | Jamie | Math | NULL |

### 🚨 Issues
- Multiple values in a single row
- Difficult to add more courses
- Violates **1NF (First Normal Form)**

---

### ✅ After Row-Level Normalization (Solution)

| StudentID | Name | Course |
|---------|------|--------|
| 1 | Alex | Math |
| 1 | Alex | Science |
| 2 | Jamie | Math |

### ✔ Benefits
- Each row stores only **one value per attribute**
- Easy to insert new courses
- Eliminates repeating groups

---

## 🧩 Column-Level Normalization

### 🔍 What is Column-Level Normalization?
Column-level normalization focuses on **removing redundant columns** and ensuring that:
- Each column depends only on the **primary key**
- No unnecessary or derived data is stored

---

### ❌ Before Column-Level Normalization (Problem)

| OrderID | Product | UnitPrice | Quantity | TotalPrice |
|--------|---------|-----------|----------|------------|
| 101 | Laptop | 500 | 2 | 1000 |
| 102 | Mouse | 20 | 3 | 60 |

### 🚨 Issues
- `TotalPrice` can be calculated
- If `UnitPrice` changes, `TotalPrice` must be updated
- Causes **update anomalies**

---

### ✅ After Column-Level Normalization (Solution)

| OrderID | Product | UnitPrice | Quantity |
|--------|---------|-----------|----------|
| 101 | Laptop | 500 | 2 |
| 102 | Mouse | 20 | 3 |

> `TotalPrice = UnitPrice × Quantity` (calculated when needed)

### ✔ Benefits
- No redundant or derived columns
- Prevents inconsistent data
- Cleaner database design

---

## 📊 Comparison Table

| Aspect | Row-Level Normalization | Column-Level Normalization |
|------|------------------------|---------------------------|
| Focus | Duplicate rows / repeating data | Redundant or dependent columns |
| Main Goal | One fact per row | One dependency per column |
| Related To | 1NF | 2NF & 3NF |
| Prevents | Insertion & deletion anomalies | Update anomalies |

---

## 🏁 Conclusion
- **Row-level normalization** ensures clean and atomic rows
- **Column-level normalization** ensures meaningful and non-redundant columns
- Together, they create a well-structured and reliable database

Understanding normalization this way makes it easier to design databases **before** applying formal normal forms.

---

## 📖 References
- Database Management Systems
- Relational Database Design Concepts
