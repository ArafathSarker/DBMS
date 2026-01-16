# Fifth Normal Form (5NF) in DBMS

## Introduction
Fifth Normal Form (5NF), also known as **Projection-Join Normal Form (PJNF)**, is a high-level normalization used to handle cases where **information can be reconstructed from smaller pieces of data without redundancy**. It deals with **join dependencies** and ensures that the database is free from unnecessary redundancy caused by complex relationships.

5NF builds on **Fourth Normal Form (4NF)**.

---

## Definition of 5NF
A relation is in **Fifth Normal Form (5NF)** if:
- It is already in **Fourth Normal Form (4NF)**
- Every **join dependency** in the table is implied by the **candidate keys**
- The table cannot be decomposed further without **loss of data**

**Join dependency:**  
A table has a join dependency if it can be recreated by joining multiple smaller tables.

---

## Example of Table NOT in 5NF

### SUPPLY table

| Supplier | Part  | Project |
|---------|-------|---------|
| S1      | P1    | PR1     |
| S1      | P2    | PR1     |
| S2      | P1    | PR1     |
| S2      | P2    | PR1     |

- Each combination of Supplier, Part, and Project is valid  
- The table contains **redundancy** that can be resolved by decomposition  

---

## Decomposing Table into 5NF

### SUPPLIER_PART table

| Supplier | Part |
|---------|------|
| S1      | P1   |
| S1      | P2   |
| S2      | P1   |
| S2      | P2   |

### PART_PROJECT table

| Part | Project |
|------|--------|
| P1   | PR1    |
| P2   | PR1    |

### SUPPLIER_PROJECT table

| Supplier | Project |
|---------|--------|
| S1      | PR1    |
| S2      | PR1    |

✔ No redundancy  
✔ Table can be recombined via joins  
✔ Database is in **Fifth Normal Form (5NF)**

---

## SQL Example

```sql
CREATE TABLE SupplierPart (
    Supplier VARCHAR(10),
    Part VARCHAR(10),
    PRIMARY KEY (Supplier, Part)
);

CREATE TABLE PartProject (
    Part VARCHAR(10),
    Project VARCHAR(10),
    PRIMARY KEY (Part, Project)
);

CREATE TABLE SupplierProject (
    Supplier VARCHAR(10),
    Project VARCHAR(10),
    PRIMARY KEY (Supplier, Project)
);
```
## Advantages of Fifth Normal Form (5NF)

- Eliminates redundancy caused by join dependencies  
- Ensures lossless decomposition  
- Improves data consistency  
- Optimizes complex database relationships  

---

## Limitations of Fifth Normal Form (5NF)

- May result in too many small tables  
- Requires multiple joins for queries  
- Complex to design and maintain  
