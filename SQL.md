# Introduction to SQL: Basics, Joins and Aggregations

## Introduction

SQL stands for Structured Query Language. It is used to store, read and change data in relational databases. A database keeps its data in tables, and each table has rows and columns. In this paper, I explain three main ideas with small examples.

## Basics

The `SELECT` command reads data from a table. The `WHERE` clause keeps only the rows that match a condition. The example below shows the name and salary of employees who earn more than 50000.

```sql
SELECT name, salary
FROM employees
WHERE salary > 50000
ORDER BY salary DESC;

INSERT INTO employees (name, salary, dept_id)
VALUES ('Asha', 60000, 2);

UPDATE employees SET salary = 65000 WHERE name = 'Asha';

DELETE FROM employees WHERE name = 'Asha';
```

* `SELECT` reads the chosen columns from a table.
* `WHERE` keeps only the rows that match a condition.
* `ORDER BY` sorts the result in ascending or descending order.
* `INSERT` adds a new row to a table.
* `UPDATE` changes the values in existing rows.
* `DELETE` removes rows from a table.

## Joins

Real data is often spread across many tables. A join combines two tables by using a common column. An `INNER JOIN` returns only the rows that match in both tables. A `LEFT JOIN` returns all rows from the left table, even when there is no match.

```sql
SELECT e.name, d.dept_name
FROM employees e
INNER JOIN departments d ON e.dept_id = d.id;

SELECT d.dept_name, e.name
FROM departments d
LEFT JOIN employees e ON d.id = e.dept_id;
```

* `INNER JOIN` returns only the rows that have a match in both tables.
* `LEFT JOIN` returns all rows from the left table and fills missing matches with NULL.

## Aggregations

Aggregate functions work on many rows and return one value. The `GROUP BY` clause makes one result for each group. The example below counts the employees in each department.

```sql
SELECT dept_id, COUNT(*) AS total_staff, AVG(salary) AS average_salary
FROM employees
GROUP BY dept_id
HAVING AVG(salary) > 40000;
```

* `COUNT` gives the number of rows.
* `SUM` adds up the values of a column.
* `AVG` gives the average value of a column.
* `MIN` gives the smallest value of a column.
* `MAX` gives the largest value of a column.
* `GROUP BY` splits the rows into groups so each group gets one result.
* `HAVING` filters the groups after they are formed.

## Conclusion

SQL is easy to learn when we start with small steps. Basic queries read data, joins connect tables and aggregations give useful summaries. Regular practice makes these ideas simple.

## References

* [W3Schools: SQL Tutorial](https://www.w3schools.com/sql/)
* [W3Schools: SQL Joins](https://www.w3schools.com/sql/sql_join.asp)
* [W3Schools: SQL GROUP BY](https://www.w3schools.com/sql/sql_groupby.asp)
* [GeeksforGeeks: SQL Tutorial](https://www.geeksforgeeks.org/sql-tutorial/)