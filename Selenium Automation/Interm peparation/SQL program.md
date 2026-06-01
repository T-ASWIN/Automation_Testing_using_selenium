1.Basics

CREATE TABLE Students (
    ID INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT
);

2.alter

ALTER TABLE Students
ADD Grade VARCHAR(10);

ALTER TABLE Students
MODIFY Name VARCHAR(100);

ALTER TABLE Students
DROP COLUMN Age;

3.DROP

DROP TABLE Students;

4.TRUNCATE 

TRUNCATE TABLE Students;

5.INSERT

INSERT INTO Students (ID, Name, Age)
VALUES (1, 'Aswin', 22);

6.UPDATE

UPDATE Students
SET Age = 23
WHERE ID = 1;

7.DELETE

DELETE FROM Students
WHERE ID = 1;

8.select

SELECT * FROM Students;
