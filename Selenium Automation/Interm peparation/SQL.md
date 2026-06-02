1. what is SQL

Structured Query Language (SQL) is the standard language used to interact with relational databases.

It allows users to store, retrieve, update and manage data efficiently through simple commands.
It is known for its user-friendly syntax and powerful capabilities, SQL is widely used across industries.

***


# 🔷2. Difference Between DELETE, TRUNCATE, and DROP

## ✅ 1. DELETE

### 🔹 What it does

* Removes **specific rows** from a table

### 🔹 Example

```sql
DELETE FROM Students
WHERE ID = 1;
```

### 🔹 Key Points

* You can delete **selected records** using `WHERE`
* Slower (removes rows one by one)
* **Can be rolled back**
* Table structure remains

***

## ✅ 2. TRUNCATE

### 🔹 What it does

* Removes **all rows** from a table (completely clears data)

### 🔹 Example

```sql
TRUNCATE TABLE Students;
```

### 🔹 Key Points

* Cannot use `WHERE` → deletes all records
* Faster than DELETE
* **Cannot be rolled back** (in most databases)
* Table structure remains
* Resets **auto-increment values**

***

## ✅ 3. DROP

### 🔹 What it does

* Deletes **entire table** including structure and data

### 🔹 Example

```sql
DROP TABLE Students;
```

### 🔹 Key Points

* Removes table completely
* Data + structure both deleted
* **Cannot be rolled back**
* Table must be recreated to use again

***

# 🔥 Comparison Table (Very Important)

| Feature              | DELETE      | TRUNCATE        | DROP                    |
| -------------------- | ----------- | --------------- | ----------------------- |
| Purpose              | Delete rows | Remove all data | Delete table completely |
| WHERE clause         | ✅ Yes       | ❌ No            | ❌ No                    |
| Speed                | Slow        | Fast            | Very fast               |
| Rollback             | ✅ Yes       | ❌ No (mostly)   | ❌ No                    |
| Structure            | Remains     | Remains         | Deleted                 |
| Auto-increment reset | ❌ No        | ✅ Yes           | ✅ Yes (full removal)    |
| Type                 | DML         | DDL             | DDL                     |

***

# ✅ Simple Memory Trick

* **DELETE** → Removes *some data*
* **TRUNCATE** → Removes *all data*
* **DROP** → Removes *everything (table itself)*

***



# 🔷3.  Types of Joins in SQL

SQL joins are broadly divided into **two categories**:

## ✅ 1. Based on Result (Main Joins)

## ✅ 2. Based on Condition (Special Joins)

***

# ✅ 1. MAIN TYPES OF JOINS

***

## 🔶 1. INNER JOIN

### ✅ Definition

Returns **only matching rows** from both tables.

***

### 🔹 Example

```sql
SELECT s.Name, m.Marks
FROM Students s
INNER JOIN Marks m
ON s.ID = m.ID;
```

***

### ✅ Output

```
Aswin  85
Ram    90
```

✔ Only common data

***

## 🔶 2. LEFT JOIN (LEFT OUTER JOIN)

### ✅ Definition

Returns **all rows from left table** + matching rows from right table.

***

### 🔹 Example

```sql
SELECT s.Name, m.Marks
FROM Students s
LEFT JOIN Marks m
ON s.ID = m.ID;
```

***

### ✅ Output

```
Aswin  85
Ram    90
Ravi   NULL
```

✔ All left table data, even if no match

***

## 🔶 3. RIGHT JOIN (RIGHT OUTER JOIN)

### ✅ Definition

Returns **all rows from right table** + matching rows from left table.

***

### 🔹 Example

```sql
SELECT s.Name, m.Marks
FROM Students s
RIGHT JOIN Marks m
ON s.ID = m.ID;
```

***

### ✅ Output

```
Aswin  85
Ram    90
NULL   75
```

✔ All right table data

***

## 🔶 4. FULL JOIN (FULL OUTER JOIN)

### ✅ Definition

Returns **all rows from both tables**, matched where possible.

***

### 🔹 Example

```sql
SELECT s.Name, m.Marks
FROM Students s
FULL JOIN Marks m
ON s.ID = m.ID;
```

***

### ✅ Output

```
Aswin  85
Ram    90
Ravi   NULL
NULL   75
```

✔ Includes unmatched rows from both

***

## 🔶 5. CROSS JOIN

### ✅ Definition

Returns **Cartesian product** (all combinations).

***

### 🔹 Example

```sql
SELECT s.Name, m.Marks
FROM Students s
CROSS JOIN Marks m;
```

***

### ✅ Output

Every row combines with every row.

***

## 🔶 6. SELF JOIN

### ✅ Definition

A table is joined with **itself**.

***

### 🔹 Example

```sql
SELECT A.Name, B.Name
FROM Students A, Students B
WHERE A.ID <> B.ID;
```

✔ Used for comparing rows within same table

***

# ✅ 2. SPECIAL TYPES OF JOINS (Based on Condition)

***

## 🔷 7. EQUI JOIN

### ✅ Definition

Join using **only `=` operator**

***

### 🔹 Example

```sql
SELECT *
FROM Students s, Marks m
WHERE s.ID = m.ID;
```

✔ Most common join

***

## 🔷 8. THETA JOIN (CONDITIONAL JOIN)

### ✅ Definition

Join using **any operator** (`<, >, <=, >=, !=`)

***

### 🔹 Example

```sql
SELECT *
FROM Students s, Marks m
WHERE s.ID > m.ID;
```

✔ Flexible conditions

***

## 🔷 9. NATURAL JOIN

### ✅ Definition

Automatically joins tables with **same column names**

***

### 🔹 Example

```sql
SELECT *
FROM Students
NATURAL JOIN Marks;
```

✔ No need for `ON`

***

# 🔥 FINAL SUMMARY TABLE

| Join Type    | Description               |
| ------------ | ------------------------- |
| INNER JOIN   | Only matching rows        |
| LEFT JOIN    | All left + matching right |
| RIGHT JOIN   | All right + matching left |
| FULL JOIN    | All records from both     |
| CROSS JOIN   | All combinations          |
| SELF JOIN    | Table joins itself        |
| EQUI JOIN    | Join using `=`            |
| THETA JOIN   | Join using conditions     |
| NATURAL JOIN | Auto join on same column  |

***

# ✅ Easy Memory Trick

* **INNER** → Common
* **LEFT/RIGHT** → One side full
* **FULL** → Everything
* **CROSS** → All combinations
* **EQUI** → `=`
* **THETA** → Any condition
* **NATURAL** → Automatic

***

## 🔷4. What are Keys in SQL?

**Keys** are database constraints used to **identify records uniquely and maintain relationships between tables**.

👉 In simple terms:  
**Keys = Rules used to uniquely identify data and link tables**

***

# 🔷 Types of Keys in SQL

***

## ✅ 1. Primary Key

### 🔹 Definition

A **Primary Key** is a column (or combination of columns) that **uniquely identifies each record in a table**.

***

### 🔹 Example

```sql
CREATE TABLE Students (
    ID INT PRIMARY KEY,
    Name VARCHAR(50)
);
```

***

### 🔹 Key Points

* Must be **unique**
* Cannot contain **NULL values**
* Only **one primary key per table**

***

## ✅ 2. Foreign Key

### 🔹 Definition

A **Foreign Key** is a column that creates a **relationship between two tables**.

***

### 🔹 Example

```sql
CREATE TABLE Marks (
    ID INT,
    Marks INT,
    FOREIGN KEY (ID) REFERENCES Students(ID)
);
```

***

### 🔹 Key Points

* References **Primary Key in another table**
* Can have duplicate and NULL values
* Maintains **referential integrity**

***

## ✅ 3. Candidate Key

### 🔹 Definition

A **Candidate Key** is a column that **can become a primary key**.

***

### 🔹 Example

```
ID, Email → both can uniquely identify records
```

***

### 🔹 Key Points

* Multiple candidate keys possible
* One is chosen as primary key

***

## ✅ 4. Super Key

### 🔹 Definition

A **Super Key** is any combination of columns that **uniquely identifies a record**.

***

### 🔹 Example

```
ID
ID + Name
ID + Name + Age
```

***

### 🔹 Key Points

* Can have **extra unnecessary columns**
* Superset of candidate keys

***

## ✅ 5. Alternate Key

### 🔹 Definition

Candidate keys that are **not selected as primary key**.

***

### 🔹 Example

```
ID → Primary Key  
Email → Alternate Key
```

***

### 🔹 Key Points

* Secondary unique keys
* Can be used for searching

***

## ✅ 6. Composite Key (Compound Key)

### 🔹 Definition

A key made of **two or more columns together**.

***

### 🔹 Example

```sql
CREATE TABLE Orders (
    OrderID INT,
    ProductID INT,
    PRIMARY KEY (OrderID, ProductID)
);
```

***

### 🔹 Key Points

* Used when single column is not enough
* Combination must be unique

***

## ✅ 7. Unique Key

### 🔹 Definition

Ensures all values in a column are **unique**.

***

### 🔹 Example

```sql
CREATE TABLE Users (
    Email VARCHAR(50) UNIQUE
);
```

***

### 🔹 Key Points

* No duplicate values allowed
* Can have **one NULL value** (depends on DB)

***

## ✅ 8. Surrogate Key

### 🔹 Definition

A **system-generated key** (like auto-increment ID).

***

### 🔹 Example

```sql
ID INT AUTO_INCREMENT PRIMARY KEY
```

***

### 🔹 Key Points

* No business meaning
* Used for simplicity and performance

***

# 🔥 Summary Table

| Key Type      | Purpose                     |
| ------------- | --------------------------- |
| Primary Key   | Uniquely identifies records |
| Foreign Key   | Links two tables            |
| Candidate Key | Possible primary keys       |
| Super Key     | Any unique combination      |
| Alternate Key | Unused candidate keys       |
| Composite Key | Multiple columns as key     |
| Unique Key    | Ensures uniqueness          |
| Surrogate Key | Auto-generated key          |

***

# ✅ Easy Memory Trick

* **Primary** → Main unique
* **Foreign** → From another table
* **Candidate** → Can become primary
* **Composite** → Combination
* **Unique** → No duplicates
* **Super** → Everything unique
* **Alternate** → Backup key

***
# 5. **ORDER BY**, **GROUP BY**, and **HAVING** 

***

# 🔷 1. ORDER BY

## ✅ Definition

`ORDER BY` is used to **sort the result (output)** of a query.

👉 It does **not change data**, only the way it is displayed.

***

## 🔹 Syntax

```sql
SELECT column_name
FROM table_name
ORDER BY column_name ASC|DESC;
```

***

## 🔹 Example

```sql
SELECT Name, Age
FROM Students
ORDER BY Age ASC;
```

***

## ✅ Output

Sorted by age (small to large)

***

## 🔹 Key Points

* `ASC` → Ascending (default)
* `DESC` → Descending
* Can sort by multiple columns

```sql
ORDER BY Age ASC, Name DESC;
```

***

# 🔷 2. GROUP BY

## ✅ Definition

`GROUP BY` is used to **group rows that have the same values** into summary results.

👉 Mostly used with **aggregate functions** like:

* COUNT()
* SUM()
* AVG()
* MIN()
* MAX()

***

## 🔹 Syntax

```sql
SELECT column_name, aggregate_function(column)
FROM table_name
GROUP BY column_name;
```

***

## 🔹 Example

```sql
SELECT Age, COUNT(*)
FROM Students
GROUP BY Age;
```

***

## ✅ Output

```
Age | Count
22  | 3
23  | 2
```

✔ Groups students by age

***

## 🔹 Key Points

* Used with aggregate functions
* Groups similar values together

***

# 🔷 3. HAVING

## ✅ Definition

`HAVING` is used to **filter grouped data** (after GROUP BY).

👉 Works like `WHERE`, but for groups.

***

## 🔹 Syntax

```sql
SELECT column_name, aggregate_function(column)
FROM table_name
GROUP BY column_name
HAVING condition;
```

***

## 🔹 Example

```sql
SELECT Age, COUNT(*)
FROM Students
GROUP BY Age
HAVING COUNT(*) > 2;
```

***

## ✅ Output

Shows only groups where count > 2

***

## 🔹 Key Points

* Used **after GROUP BY**
* Works with aggregate functions
* Filters grouped results

***

# 🔥 Difference Between WHERE and HAVING

| Feature              | WHERE           | HAVING       |
| -------------------- | --------------- | ------------ |
| Works on             | Rows            | Groups       |
| Used before GROUP BY | ✅ Yes           | ❌ No         |
| Used with aggregates | ❌ No            | ✅ Yes        |
| Filters              | Individual rows | Grouped data |

***

# 🔥 Combined Example (IMPORTANT)

```sql
SELECT Age, COUNT(*) AS Total
FROM Students
WHERE Age > 20
GROUP BY Age
HAVING COUNT(*) > 1
ORDER BY Total DESC;
```

***

## ✅ Execution Order (Very Important 👇)

1. `WHERE` → filters rows
2. `GROUP BY` → groups data
3. `HAVING` → filters groups
4. `ORDER BY` → sorts final result

***

# ✅ Easy Memory Trick

* **ORDER BY** → Sort data
* **GROUP BY** → Group data
* **HAVING** → Filter groups

In SQL (Structured Query Language), commands are grouped into different categories based on what they do.

***

# 🔹 Main SQL Command Types

## 1. DDL – Data Definition Language

👉 Used to **define or modify database structure**

### Commands:

* `CREATE` → create table/database
* `ALTER` → modify structure
* `DROP` → delete table/database
* `TRUNCATE` → remove all records (faster than DELETE)

### Example:

```sql
CREATE TABLE students (
  id INT,
  name VARCHAR(50)
);

ALTER TABLE students ADD age INT;

DROP TABLE students;
```

***

## 2. DML – Data Manipulation Language

👉 Used to **change data inside the table**

### Commands:

* `INSERT` → add data
* `UPDATE` → modify data
* `DELETE` → remove data

### Example:

```sql
INSERT INTO students VALUES (1, 'Aswin');

UPDATE students SET name = 'John' WHERE id = 1;

DELETE FROM students WHERE id = 1;
```

***

## 3. DQL – Data Query Language

👉 Used to **retrieve (fetch) data**

### Command:

* `SELECT`

### Example:

```sql
SELECT * FROM students;

SELECT name FROM students WHERE id = 1;
```

***

## 4. DCL – Data Control Language

👉 Used to **control permissions (access rights)**

### Commands:

* `GRANT` → give permission
* `REVOKE` → remove permission

### Example:

```sql
GRANT SELECT ON students TO user1;

REVOKE SELECT ON students FROM user1;
```

***

## 5. TCL – Transaction Control Language

👉 Used to **manage transactions (save/undo changes)**

### Commands:

* `COMMIT` → save permanently
* `ROLLBACK` → undo changes
* `SAVEPOINT` → create restore point

### Example:

```sql
BEGIN;

UPDATE students SET name = 'Ram';

SAVEPOINT s1;

ROLLBACK TO s1;

COMMIT;
```

***

# 🔹 Simple Summary Table

| Type | Full Form                    | Purpose                   |
| ---- | ---------------------------- | ------------------------- |
| DDL  | Data Definition Language     | Structure (tables)        |
| DML  | Data Manipulation Language   | Insert/Update/Delete data |
| DQL  | Data Query Language          | Fetch data                |
| DCL  | Data Control Language        | Permissions               |
| TCL  | Transaction Control Language | Save/Undo changes         |

***


