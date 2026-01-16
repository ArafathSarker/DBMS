# Normal Forms (NF) Shortcuts – Exam Notes

- **1NF (First Normal Form)** = Atomic values, no repeating groups  
- **2NF (Second Normal Form)** = 1NF + No partial dependency  
- **3NF (Third Normal Form)** = 2NF + No transitive dependency  
- **BCNF (Boyce–Codd Normal Form)** = 3NF + Every determinant is a candidate key  
- **4NF (Fourth Normal Form)** = BCNF + No multi-valued dependencies  
- **5NF (Fifth Normal Form / PJNF)** = 4NF + No join dependency  

---

### Quick Memory Tips:
- **1NF** → Atomic  
- **2NF** → Full key dependency  
- **3NF** → Non-key attributes depend only on primary key  
- **BCNF** → Determinant must be a key  
- **4NF** → Remove independent multi-values  
- **5NF** → Tables join without redundancy  
