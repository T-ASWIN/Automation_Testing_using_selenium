
***

## 1. What is PRIMARY KEY in SQL?

A **PRIMARY KEY** is used to **uniquely identify each record (row)** in a table.

### Rules of PRIMARY KEY

*   **Must be unique** (no duplicate values)
*   **Cannot be NULL**
*   A table can have **only one PRIMARY KEY**
*   Can be **single column** or **multiple columns (composite key)**

***

### Example: PRIMARY KEY

```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT
);
```

✅ `StudentID` uniquely identifies each student  
❌ You cannot insert duplicate or NULL `StudentID`

```sql
INSERT INTO Students VALUES (1, 'Aswin', 22);   -- OK
INSERT INTO Students VALUES (1, 'Rahul', 23);   -- ERROR (duplicate)
INSERT INTO Students VALUES (NULL, 'Ravi', 21); -- ERROR (NULL)
```

***

## 2. Similar Concepts to PRIMARY KEY

***

## 2.1 UNIQUE Constraint

Ensures values are **unique**, but **NULL is allowed**.

### Example: UNIQUE

```sql
CREATE TABLE Employees (
    EmpID INT PRIMARY KEY,
    Email VARCHAR(100) UNIQUE
);
```

✅ Email must be unique  
✅ Multiple NULL values are allowed (depends on DB)

```sql
INSERT INTO Employees VALUES (1, 'a@company.com');
INSERT INTO Employees VALUES (2, 'a@company.com'); -- ERROR
INSERT INTO Employees VALUES (3, NULL);            -- OK
```

🔍 Difference from PRIMARY KEY:

| PRIMARY KEY        | UNIQUE           |
| ------------------ | ---------------- |
| No NULL            | NULL allowed     |
| Only one per table | Multiple allowed |

***

## 2.2 FOREIGN KEY

A **FOREIGN KEY** is used to **link two tables**.

It refers to a **PRIMARY KEY in another table**.

***

### Example: FOREIGN KEY

```sql
CREATE TABLE Departments (
    DeptID INT PRIMARY KEY,
    DeptName VARCHAR(50)
);

CREATE TABLE Employees (
    EmpID INT PRIMARY KEY,
    Name VARCHAR(50),
    DeptID INT,
    FOREIGN KEY (DeptID) REFERENCES Departments(DeptID)
);
```

✅ Ensures employee belongs to a **valid department**

```sql
INSERT INTO Departments VALUES (1, 'IT');

INSERT INTO Employees VALUES (101, 'Aswin', 1); -- OK
INSERT INTO Employees VALUES (102, 'Rahul', 5); -- ERROR (Dept 5 not exists)
```

***

## 2.3 NOT NULL Constraint

Prevents **NULL values** in a column.

```sql
CREATE TABLE Users (
    UserID INT PRIMARY KEY,
    Username VARCHAR(50) NOT NULL
);
```

```sql
INSERT INTO Users VALUES (1, NULL); -- ERROR
```

✅ PRIMARY KEY **automatically includes NOT NULL**

***

## 2.4 COMPOSITE PRIMARY KEY (Multiple Columns)

When **more than one column together** forms the primary key.

***

### Example: Composite PRIMARY KEY

```sql
CREATE TABLE CourseEnrollments (
    StudentID INT,
    CourseID INT,
    PRIMARY KEY (StudentID, CourseID)
);
```

✅ Same student can’t enroll in same course twice  
✅ But student can enroll in multiple courses

***

## 2.5 CANDIDATE KEY

A **candidate key** is any column that **can become a primary key**.

Example:

```text
StudentID
Email
AadharNumber
```

If `StudentID` is chosen as primary key,  
`Email` and `AadharNumber` are **candidate keys**.

***

## 2.6 ALTERNATE KEY

The candidate keys **not chosen** as primary key.

Example:

*   Primary Key → `StudentID`
*   Alternate Key → `Email`

Usually implemented using `UNIQUE`.

***

## 2.7 INDEX (Related but Different)

An **INDEX** improves search speed (not for uniqueness unless specified).

```sql
CREATE INDEX idx_name ON Students(Name);
```

✅ Faster queries  
❌ Does not enforce uniqueness by default

***

## Quick Summary

| Concept       | Purpose                      |
| ------------- | ---------------------------- |
| PRIMARY KEY   | Unique + Not Null identifier |
| UNIQUE        | Prevent duplicates           |
| FOREIGN KEY   | Link tables                  |
| NOT NULL      | Disallow NULL values         |
| COMPOSITE KEY | Multi-column primary key     |
| CANDIDATE KEY | Possible primary keys        |
| ALTERNATE KEY | Candidate but not selected   |
| INDEX         | Faster searching             |

***

