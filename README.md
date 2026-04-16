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
