# 🎯 Normal Forms (NF) – Quick Exam Notes

---

## 1️⃣ First Normal Form (1NF)

**Rule:**

* All values must be **atomic (indivisible)**
* No repeating groups or multi-valued attributes

**Keyword:** *Atomicity*

---

## 2️⃣ Second Normal Form (2NF)

**Rule:**

* Must be in **1NF**
* No **partial dependency**

  * Every non-key attribute must depend on the **whole primary key**, not just part of it

**Keyword:** *Full key dependency*

---

## 3️⃣ Third Normal Form (3NF)

**Rule:**

* Must be in **2NF**
* No **transitive dependency**

  * Non-key attributes should depend **only on the primary key**, not on other non-key attributes

**Keyword:** *Only on the key*

---

## 🅱️ Boyce–Codd Normal Form (BCNF)

**Rule:**

* Must be in **3NF**
* **Every determinant must be a candidate key**

**Keyword:** *Determinant = Key*

---

## 4️⃣ Fourth Normal Form (4NF)

**Rule:**

* Must be in **BCNF**
* No **multi-valued dependencies**

  * Remove independent multi-valued facts about an entity

**Keyword:** *No independent multi-values*

---

## 5️⃣ Fifth Normal Form (5NF / PJNF)

**Rule:**

* Must be in **4NF**
* No **join dependencies**

  * Table cannot be further decomposed without losing information

**Keyword:** *No redundancy after joins*

---

# 🧠 Ultra-Short Memory Chain

| NF   | Think           |
| ---- | --------------- |
| 1NF  | Atomic          |
| 2NF  | Full key        |
| 3NF  | Only key        |
| BCNF | Key rule        |
| 4NF  | One multi-value |
| 5NF  | Perfect join    |

---

Perfect for last-minute revision before exams ✅
Want a few examples for each form next?
