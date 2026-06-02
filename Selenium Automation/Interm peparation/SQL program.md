Great 👍 — you’ve collected important SQL topics. Let me organize everything into a **clean, structured revision sheet (cheat sheet)** so you can easily study or use it in interviews.

***

# ✅ 🔷 SQL COMPLETE QUICK REVISION

***

# 🔹 1. TABLE OPERATIONS (DDL)

## ✅ Create Table

```sql
CREATE TABLE Students (
    ID INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT
);
```

***

## ✅ ALTER Table

### Add Column

```sql
ALTER TABLE Students
ADD Grade VARCHAR(10);
```

### Modify Column

```sql
ALTER TABLE Students
MODIFY Name VARCHAR(100);
```

### Drop Column

```sql
ALTER TABLE Students
DROP COLUMN Age;
```

***

## ✅ DROP Table

```sql
DROP TABLE Students;
```

✔ Deletes structure + data

***

## ✅ TRUNCATE Table

```sql
TRUNCATE TABLE Students;
```

✔ Deletes all data but keeps structure

***

# 🔹 2. DATA OPERATIONS (DML)

## ✅ INSERT

```sql
INSERT INTO Students (ID, Name, Age)
VALUES (1, 'Aswin', 22);
```

***

## ✅ UPDATE

```sql
UPDATE Students
SET Age = 23
WHERE ID = 1;
```

***

## ✅ DELETE

```sql
DELETE FROM Students
WHERE ID = 1;
```

***

# 🔹 3. DATA RETRIEVAL (DQL)

## ✅ SELECT

```sql
SELECT * FROM Students;
```

### Specific columns

```sql
SELECT Name, Age FROM Students;
```

***

# 🔹 4. IMPORTANT QUERIES

***

## ✅ Second Highest Salary

### Method 1 (MAX)

```sql
SELECT MAX(Salary)
FROM Employees
WHERE Salary < (SELECT MAX(Salary) FROM Employees);
```

***

### Method 2 (ORDER BY)

```sql
SELECT DISTINCT Salary
FROM Employees
ORDER BY Salary DESC
LIMIT 1 OFFSET 1;
```

***

## ✅ Salary > 10000 from Two Tables

### Using JOIN

```sql
SELECT e.Name, e.Salary, d.DepartmentName
FROM Employees e
JOIN Departments d
ON e.DeptID = d.DeptID
WHERE e.Salary > 10000;
```

***

### Using UNION

```sql
SELECT Name, Salary FROM Employees1 WHERE Salary > 10000
UNION
SELECT Name, Salary FROM Employees2 WHERE Salary > 10000;
```

***

# 🔹 5. SORTING

## ✅ Descending Order

```sql
SELECT * 
FROM Employees
ORDER BY Salary DESC;
```

***

# 🔹 6. KEY CONCEPT SUMMARY

***

## 🔸 DELETE vs TRUNCATE vs DROP

* DELETE → Removes selected rows
* TRUNCATE → Removes all rows
* DROP → Deletes table completely

***

## 🔸 JOIN Default

```sql
JOIN = INNER JOIN ✅
```

***

