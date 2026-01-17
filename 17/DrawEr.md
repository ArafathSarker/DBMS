# How to Draw an ER Diagram (Entity Relationship Diagram)

This guide explains step-by-step how to draw a clear and correct **Entity Relationship (ER) Diagram** for database design.

---

## What is an ER Diagram?

An **ER Diagram** is a visual representation of a database structure. It shows:

* **Entities** (tables)
* **Attributes** (columns)
* **Relationships** (connections between tables)

ER diagrams are used in planning databases before writing SQL.

---

## Step 1: Identify the Entities

Entities represent real-world objects or concepts.

Examples:

* Student
* Course
* Teacher
* Order
* Product

Each entity will become a table in the database.

### How to choose entities

Ask:

* What objects do I need to store data about?
* What nouns appear in the system description?

---

## Step 2: Add Attributes to Each Entity

Attributes are the properties of an entity.

Example:

**Student**

* student_id
* name
* email
* date_of_birth

**Course**

* course_id
* course_name
* credits

---

## Step 3: Choose Primary Keys

A **Primary Key (PK)** uniquely identifies each record in an entity.

Rules for a good primary key:

* Unique
* Not null
* Never changes

Example:

* Student → `student_id (PK)`
* Course → `course_id (PK)`

Mark primary keys clearly in the diagram.

---

## Step 4: Identify Relationships

Relationships show how entities are connected.

Examples:

* Student **enrolls in** Course
* Teacher **teaches** Course
* Customer **places** Order

Write the relationship as a verb phrase.

---

## Step 5: Define Cardinality

Cardinality shows how many records are involved.

Common types:

| Type | Meaning      |
| ---- | ------------ |
| 1:1  | One to One   |
| 1:N  | One to Many  |
| M:N  | Many to Many |

Examples:

* One teacher teaches many courses (1:N)
* Many students enroll in many courses (M:N)

---

## Step 6: Resolve Many-to-Many Relationships

Databases cannot directly store M:N relationships.

Create a **junction table**.

Example:

Student ↔ Course (M:N)

Create:

**Enrollment**

* enrollment_id (PK)
* student_id (FK)
* course_id (FK)
* grade

Now you have:

* Student 1:N Enrollment
* Course 1:N Enrollment

---

## Step 7: Add Foreign Keys

A **Foreign Key (FK)** links two tables.

Example:

* Enrollment.student_id → Student.student_id
* Enrollment.course_id → Course.course_id

Foreign keys enforce relationships in the database.

---

## Step 8: Draw the Diagram

Use standard ER symbols:

| Symbol               | Meaning      |
| -------------------- | ------------ |
| Rectangle            | Entity       |
| Oval                 | Attribute    |
| Diamond              | Relationship |
| Underlined attribute | Primary Key  |

Or in Crow’s Foot notation:

* `|` = one
* `O` = optional
* `<` = many

---

## Example ER Diagram (Text Form)

```
Student (student_id PK, name, email)
        |
        | 1:N
        |
Enrollment (enrollment_id PK, student_id FK, course_id FK, grade)
        |
        | N:1
        |
Course (course_id PK, course_name, credits)
```

---

## Tools to Draw ER Diagrams

Free tools:

* draw.io (diagrams.net)
* Lucidchart
* dbdiagram.io
* MySQL Workbench

---

## Best Practices

* Use clear, meaningful names
* Do not duplicate data across tables
* Always define primary keys
* Break M:N relationships into junction tables
* Keep diagrams simple and readable

---

## Conclusion

ER diagrams help you design databases correctly before coding.
A good ER diagram saves time and prevents data problems later.

---

**Author:** Your Name
**License:** MIT
