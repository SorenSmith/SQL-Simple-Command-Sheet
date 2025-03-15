# SQL-Simple-Command-Sheet
I am deciding to create this because every time I look up some simple command sheet for SQL I can never manage to find a very simple, dumbed-down version to help me become more efficient at coding. I do not know about everyone else, but for me, I know what all the commands do. however, whenever it comes to remembering them off the top of my head Since I am new I still struggle and would greatly appreciate a place to go to just get a reminder occasionally. So I am going to slowly make a database of all the commands and what they do.

Then maybe  later create an example area for each command however I do not know if that will be necessary. 

# SQL Commands Reference

| **Command**       | **Description**                                           | **Example** |
|-------------------|-----------------------------------------------------------|-------------|
| `SELECT`         | Retrieves data from one or more tables.                     | `SELECT * FROM employees;` |
| `INSERT INTO`    | Adds new rows of data to a table.                           | `INSERT INTO employees (id, name, age) VALUES (1, 'John Doe', 30);` |
| `UPDATE`         | Modifies existing records in a table.                       | `UPDATE employees SET age = 31 WHERE id = 1;` |
| `DELETE`         | Removes records from a table.                               | `DELETE FROM employees WHERE id = 1;` |
| `CREATE TABLE`   | Defines a new table structure.                              | `CREATE TABLE employees (id INT PRIMARY KEY, name VARCHAR(50), age INT);` |
| `ALTER TABLE`    | Modifies an existing table (add, delete, modify columns).   | `ALTER TABLE employees ADD COLUMN salary DECIMAL(10,2);` |
| `DROP TABLE`     | Deletes a table and all its data.                           | `DROP TABLE employees;` |
| `TRUNCATE TABLE` | Deletes all rows from a table but keeps its structure.      | `TRUNCATE TABLE employees;` |
| `CREATE DATABASE` | Creates a new database.                                    | `CREATE DATABASE company;` |
| `DROP DATABASE`  | Deletes an entire database.                                | `DROP DATABASE company;` |
| `JOIN`           | Combines rows from multiple tables based on a related column. | `SELECT employees.name, departments.name FROM employees JOIN departments ON employees.dept_id = departments.id;` |
| `LEFT JOIN`      | Returns all records from the left table and matching records from the right table. | `SELECT employees.name, departments.name FROM employees LEFT JOIN departments ON employees.dept_id = departments.id;` |
| `RIGHT JOIN`     | Returns all records from the right table and matching records from the left table. | `SELECT employees.name, departments.name FROM employees RIGHT JOIN departments ON employees.dept_id = departments.id;` |
| `FULL JOIN`      | Returns all records when there is a match in either table. | `SELECT employees.name, departments.name FROM employees FULL JOIN departments ON employees.dept_id = departments.id;` |
| `WHERE`          | Filters records based on a condition.                       | `SELECT * FROM employees WHERE age > 30;` |
| `GROUP BY`       | Groups rows with the same values in specified columns.      | `SELECT dept_id, COUNT(*) FROM employees GROUP BY dept_id;` |
| `HAVING`         | Filters groups after `GROUP BY`.                            | `SELECT dept_id, COUNT(*) FROM employees GROUP BY dept_id HAVING COUNT(*) > 5;` |
| `ORDER BY`       | Sorts results in ascending (`ASC`) or descending (`DESC`) order. | `SELECT * FROM employees ORDER BY age DESC;` |
| `LIMIT`         | Restricts the number of returned records.                   | `SELECT * FROM employees LIMIT 10;` |
| `OFFSET`        | Skips a specified number of rows before returning results.  | `SELECT * FROM employees LIMIT 10 OFFSET 5;` |
| `UNION`         | Combines result sets from two `SELECT` queries.             | `SELECT name FROM employees UNION SELECT name FROM managers;` |
| `UNION ALL`     | Combines result sets and includes duplicates.               | `SELECT name FROM employees UNION ALL SELECT name FROM managers;` |
| `EXISTS`        | Checks if a subquery returns any results.                   | `SELECT * FROM employees WHERE EXISTS (SELECT 1 FROM departments WHERE dept_id = employees.dept_id);` |
| `CASE`          | Implements conditional logic in queries.                    | `SELECT name, CASE WHEN age > 30 THEN 'Senior' ELSE 'Junior' END AS level FROM employees;` |
| `DISTINCT`      | Returns unique values in a column.                          | `SELECT DISTINCT dept_id FROM employees;` |
| `COUNT()`       | Counts the number of rows that match a condition.           | `SELECT COUNT(*) FROM employees;` |
| `AVG()`         | Calculates the average value of a numeric column.           | `SELECT AVG(salary) FROM employees;` |
| `SUM()`         | Calculates the total sum of a numeric column.               | `SELECT SUM(salary) FROM employees;` |
| `MIN()`         | Retrieves the smallest value in a column.                   | `SELECT MIN(age) FROM employees;` |
| `MAX()`         | Retrieves the largest value in a column.                    | `SELECT MAX(salary) FROM employees;` |
| `SUBQUERY`      | A query nested inside another query.                        | `SELECT name FROM employees WHERE dept_id = (SELECT id FROM departments WHERE name = 'HR');` |
| `INDEX`        | Speeds up searches in a table.                              | `CREATE INDEX idx_name ON employees(name);` |
| `VIEW`         | Creates a virtual table based on a query.                   | `CREATE VIEW employee_salaries AS SELECT name, salary FROM employees;` |
