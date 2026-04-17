![Profile view counter on GitHub](https://komarev.com/ghpvc/?username=cynthiaalfred) 

# MS-SQL
SQL Fundamentals

### Creating A Database
``` SQL
CREATE DATABASE Academic_db
CREATE DATABASE demo
```
### Selecting a Database
``` SQL
USE Academic_db
SELECT DB_NAME()
```
### Creating a Table
```SQL
CREATE TABLE students(student_id INT,name VARCHAR(100),age INT,grade INT);
```
### Checking Existing Database
```SQL
EXEC sp_help 'students'
```
### Inserting Data
```SQL
INSERT INTO students(student_id,name,age,grade)
VALUES(101,'Raju',10,5)

INSERT INTO students(student_id,name,age,grade)
VALUES(102,'sham',12,5), (103,'Baburao',14,9)

INSERT INTO students (student_id,name,age,grade)
VALUES(104,'paul',11,6)

INSERT INTO students (student_id, age,grade)
VALUES(105, 12, 7)
```
### Reading Data
```SQL
SELECT * FROM students
SELECT name FROM students
```
```SQL
UPDATE students
SET Grade = 12
WHERE student_id = 103
```
### Delete Data
```SQL
DELETE FROM students
WHERE student_id=104
```
### Truncate
```SQL
TRUNCATE table students
```
### Create Table
```SQL
CREATE TABLE staff(
emp_id INT IDENTITY(101,1) Primary key,
fname VARCHAR(50) NOT NULL,
lname VARCHAR (50) NOT NULL,
email VARCHAR(100) NOT NULL UNIQUE,
job_title VARCHAR(50) NOT NULL,
department VARCHAR(50),
salary DECIMAL(10,2) DEFAULT 30000.00,
hire_date DATE NOT NULL DEFAULT CONVERT(date,GETDATE()),
city VARCHAR(50)
);
```
```SQL
INSERT INTO staff
(fname,lname,email,job_title,department,salary,hire_date,city)
VALUES
('Aarav','Sharma','aarav.sharma@example.com','Director','Management',180000,'2019-02-10','Mumbai'),
('Diya','Patel','diya.patel@example.com','Lead Engineer','Tech',120000,'2020-08-15','Bengaluru'),
('Rohan','Mehra','rohan.mehra@example.com','Software Engineer','Tech',85000,'2022-05-20','Bengaluru'),
('Priya','Singh','priya.singh@example.com','HR Manager','Human Resources',95000,'2019-11-05','Mumbai'),
('Arjun','Kumar','arjun.kumar@example.com','Data Scientist','Tech',110000,'2021-07-12','Hyderabad'),
('Ananya','Gupta','ananya.gupta@example.com','Marketing Lead','Marketing',90000,'2020-03-01','Delhi'),
('Vikram','Reddy','vikram.reddy@example.com','Sales Executive','Sales',75000,'2023-01-30','Mumbai'),
('Sameera','Rao','sameera.rao@example.com','Software Engineer','Tech',88000,'2023-06-25','Mumbai'),
('Ishaan','Verma','ishan.varma@example.com','Recruiter','Human Resources',65000,'2022-09-01','Mumbai'),
('Kavya','Joshi','kavya.joshi@example.com','Product Designer','Design',92000,'2021-04-18','Bengaluru'),
('Zain','Khan','zain.khan@example.com','Sales Manager','Sales',115000,'2019-09-14','Delhi'),
('Nisha','Desai','nisha.desai@example.com','Jr. Data Analyst','Tech',70000,'2024-02-01','Hyderabad'),
('Aditya','Nair','aditya.nair@example.com','Marketing Analyst','Marketing',68000,'2022-10-10','Delhi'),
('Fatima','Ali','fatima.ali@example.com','Sales Executive','Sales',78000,'2022-11-22','Mumbai'),
('Kabir','Shah','kabir.shah@example.com','DevOps Engineer','Tech',105000,'2020-12-01','Pune');
```
### Where Clause
```SQL
SELECT * FROM staff WHERE emp_id = 111
SELECT * FROM staff WHERE department = 'Marketing'
SELECT * FROM staff WHERE salary  > 50000;
SELECT * FROM staff WHERE hire_date > '2020-12-31'
SELECT * FROM staff WHERE YEAR (hire_date) < 2020
SELECT * FROM staff WHERE YEAR (hire_date) > 2020
```
### Distinct
```SQL
SELECT DISTINCT department FROM staff
SELECT DISTINCT city FROM staff
```
### Order by Clause
```SQL
SELECT * FROM staff ORDER BY salary
SELECT * FROM staff ORDER BY salary DESC
```
### Like
```SQL
SELECT * FROM staff WHERE department LIKE '%Human%'
SELECT * FROM staff WHERE department LIKE '%man%'
```
### Top
```SQL
Select top 3 * from staff
SELECT TOP 3 * FROM staff ORDER BY salary 
SELECT TOP 3 * FROM staff ORDER BY salary DESC
select top 1 * from staff where department = 'Marketing'
select top 2* from staff where fname like '[AB]%'
```
### Group By Clause
```SQL
	select department from staff group by department
	select department, count(emp_id) from staff group by department
	select department, count(emp_id) as count from staff group by department
```

