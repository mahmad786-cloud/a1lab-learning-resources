# SQL Cheat Sheet

<div align="center">

# 🗄️ SQL Beginner-to-Advanced Cheat Sheet

### Quick SQL syntax and concept reference following the A1Lab SQL learning sequence.

Part of **[A1Lab Learning Resources](https://a1lab.tech)**

<br>

<a href="https://a1lab.tech/sql/introduction">
  <img
    src="https://img.shields.io/badge/Learn_SQL-A1Lab-04AA6D?style=for-the-badge&logo=mysql&logoColor=white"
    alt="Learn SQL on A1Lab"
  />
</a>

<a href="../roadmaps/sql-roadmap.md">
  <img
    src="https://img.shields.io/badge/View-SQL_Roadmap-336791?style=for-the-badge&logo=postgresql&logoColor=white"
    alt="SQL Roadmap"
  />
</a>

</div>

---

## ⚠️ SQL Dialect Note

SQL syntax can vary between database systems such as:

- MySQL
- PostgreSQL
- SQL Server
- Oracle
- SQLite

This cheat sheet uses common SQL syntax where possible.

Commands such as `SHOW DATABASES`, `USE`, `TOP`, `LIMIT`,
`FETCH FIRST`, `BACKUP DATABASE`, stored procedures, triggers,
and cursor syntax may differ between database systems.

---

## 📚 Quick Navigation

1. SQL Tutorial
2. SQL Database
3. SQL Table
4. Inserting & Modifying Data
5. Retrieving Data
6. Filtering Data
7. Constraints
8. Aggregate Functions
9. String Functions
10. Numeric Functions
11. Date Functions
12. NULL Functions
13. SQL Join
14. SQL Subquery
15. SQL Views
16. SQL Indexes
17. Advanced SQL
18. SQL Transaction
19. Database Design
20. Stored Programs
21. SQL Trigger
22. SQL Cursor
23. SQL Projects

---

# 1. SQL Tutorial

## SQL Introduction

SQL is used to work with relational databases.

Common tasks include:

```text
Create databases
Create tables
Insert data
Read data
Update data
Delete data
Filter data
Join tables
Group data
Manage transactions
```

---

## SQL Syntax

Basic query:

```sql
SELECT column_name
FROM table_name;
```

---

## SQL Statements

Examples:

```sql
SELECT * FROM students;

INSERT INTO students (name, age)
VALUES ('Ali', 20);

UPDATE students
SET age = 21
WHERE id = 1;

DELETE FROM students
WHERE id = 1;
```

---

## SQL Keywords

Common keywords:

```text
SELECT
FROM
WHERE
INSERT
UPDATE
DELETE
CREATE
ALTER
DROP
JOIN
GROUP BY
ORDER BY
HAVING
DISTINCT
```

---

## SQL Comments

Single-line:

```sql
-- This is a comment
SELECT * FROM students;
```

Multi-line:

```sql
/*
This is
a multi-line comment
*/
SELECT * FROM students;
```

---

## SQL Naming Rules

Common readable naming style:

```text
students
student_id
first_name
order_items
created_at
```

Example:

```sql
CREATE TABLE students (
    student_id INT,
    first_name VARCHAR(50)
);
```

---

## SQL Data Types

Common categories:

```text
Numeric
String
Date and Time
Boolean
```

---

## SQL Numeric Data Types

Examples:

```sql
INT
SMALLINT
BIGINT
DECIMAL(10, 2)
NUMERIC(10, 2)
FLOAT
REAL
```

Example:

```sql
price DECIMAL(10, 2)
```

---

## SQL String Data Types

Examples:

```sql
CHAR(10)
VARCHAR(100)
TEXT
```

Example:

```sql
name VARCHAR(100)
```

---

## SQL Date and Time Data Types

Common examples:

```sql
DATE
TIME
TIMESTAMP
```

Example:

```sql
created_at TIMESTAMP
```

---

## SQL Boolean Data Types

Where supported:

```sql
is_active BOOLEAN
```

---

# 2. SQL DATABASE

## CREATE Database

```sql
CREATE DATABASE school;
```

---

## SHOW Database

MySQL-style example:

```sql
SHOW DATABASES;
```

---

## USE Database

MySQL-style:

```sql
USE school;
```

---

## Rename Database

Database rename support and syntax vary by DBMS.

---

## DROP Database

```sql
DROP DATABASE school;
```

⚠️ This removes the database.

---

## BACKUP Database

Backup syntax and tooling depend on the database system.

Example SQL Server-style concept:

```sql
BACKUP DATABASE school
TO DISK = 'school_backup.bak';
```

---

## ALTER Database

Syntax depends on DBMS.

Concept:

```sql
ALTER DATABASE database_name ...;
```

---

## CREATE Schema

```sql
CREATE SCHEMA university;
```

---

## DROP Schema

```sql
DROP SCHEMA university;
```

Some systems may require:

```sql
DROP SCHEMA university CASCADE;
```

---

# 3. SQL TABLE

## CREATE Table

```sql
CREATE TABLE students (
    id INT,
    name VARCHAR(100),
    age INT
);
```

---

## ALTER Table

```sql
ALTER TABLE students
ADD email VARCHAR(100);
```

---

## Add Column

```sql
ALTER TABLE students
ADD city VARCHAR(50);
```

---

## Modify Column

Syntax varies.

Example MySQL-style:

```sql
ALTER TABLE students
MODIFY name VARCHAR(150);
```

---

## Drop Column

```sql
ALTER TABLE students
DROP COLUMN city;
```

---

## Rename Column

Common syntax:

```sql
ALTER TABLE students
RENAME COLUMN name TO full_name;
```

---

## Rename Table

```sql
ALTER TABLE students
RENAME TO learners;
```

---

## DELETE vs TRUNCATE

Delete selected rows:

```sql
DELETE FROM students
WHERE age < 18;
```

Delete all rows:

```sql
DELETE FROM students;
```

Remove all rows efficiently:

```sql
TRUNCATE TABLE students;
```

---

## DROP Table

```sql
DROP TABLE students;
```

---

## Temporary Table

```sql
CREATE TEMPORARY TABLE temp_students (
    id INT,
    name VARCHAR(100)
);
```

---

## Copy Table

Common pattern:

```sql
CREATE TABLE students_backup AS
SELECT *
FROM students;
```

---

# 4. Inserting & Modifying Data

## INSERT INTO

```sql
INSERT INTO students (id, name, age)
VALUES (1, 'Ali', 20);
```

---

## INSERT MULTIPLE ROWS

```sql
INSERT INTO students (id, name, age)
VALUES
    (1, 'Ali', 20),
    (2, 'Sara', 19),
    (3, 'Ahmed', 21);
```

---

## INSERT INTO SELECT

```sql
INSERT INTO students_backup (id, name, age)
SELECT id, name, age
FROM students;
```

---

## UPDATE

```sql
UPDATE students
SET age = 21
WHERE id = 1;
```

---

## UPDATE MULTIPLE COLUMN

```sql
UPDATE students
SET
    name = 'Muhammad Ali',
    age = 22
WHERE id = 1;
```

---

## DELETE

```sql
DELETE FROM students
WHERE id = 1;
```

⚠️ Without `WHERE`:

```sql
DELETE FROM students;
```

all rows may be removed.

---

# 5. Retrieving Data

## SELECT

```sql
SELECT *
FROM students;
```

Specific columns:

```sql
SELECT name, age
FROM students;
```

---

## SELECT DISTINCT

```sql
SELECT DISTINCT city
FROM students;
```

---

## Aliases

Column alias:

```sql
SELECT name AS student_name
FROM students;
```

Table alias:

```sql
SELECT s.name
FROM students AS s;
```

---

## ORDER BY

Ascending:

```sql
SELECT *
FROM students
ORDER BY age ASC;
```

Descending:

```sql
SELECT *
FROM students
ORDER BY age DESC;
```

---

## LIMIT

MySQL/PostgreSQL-style:

```sql
SELECT *
FROM students
LIMIT 5;
```

---

## TOP

SQL Server-style:

```sql
SELECT TOP 5 *
FROM students;
```

---

## OFFSET

```sql
SELECT *
FROM students
ORDER BY id
OFFSET 10 ROWS;
```

---

## FETCH FIRST

Common standards-style syntax:

```sql
SELECT *
FROM students
ORDER BY id
FETCH FIRST 5 ROWS ONLY;
```

---

# 6. Filtering Data

## WHERE

```sql
SELECT *
FROM students
WHERE age >= 18;
```

---

## Comparison Operators

```text
=   Equal
<>  Not equal
!=  Not equal in many systems
>   Greater than
<   Less than
>=  Greater than or equal
<=  Less than or equal
```

Example:

```sql
SELECT *
FROM products
WHERE price >= 100;
```

---

## Logical Operators

```text
AND
OR
NOT
```

---

## Arithmetic Operators

Typical operators:

```text
+
-
*
/
%
```

Example:

```sql
SELECT price * quantity AS total
FROM order_items;
```

---

## AND

```sql
SELECT *
FROM students
WHERE age >= 18
  AND city = 'Lahore';
```

---

## OR

```sql
SELECT *
FROM students
WHERE city = 'Lahore'
   OR city = 'Karachi';
```

---

## NOT

```sql
SELECT *
FROM students
WHERE NOT city = 'Lahore';
```

---

## BETWEEN

```sql
SELECT *
FROM products
WHERE price BETWEEN 100 AND 500;
```

---

## IN

```sql
SELECT *
FROM students
WHERE city IN ('Lahore', 'Karachi', 'Islamabad');
```

---

## NOT IN

```sql
SELECT *
FROM students
WHERE city NOT IN ('Lahore', 'Karachi');
```

---

## LIKE

```sql
SELECT *
FROM students
WHERE name LIKE 'A%';
```

---

## Wildcards

Common:

```text
%  Zero or more characters
_  One character
```

Examples:

```sql
WHERE name LIKE 'A%'

WHERE name LIKE '_li'
```

---

## ESCAPE

Example:

```sql
SELECT *
FROM products
WHERE code LIKE 'A\_%' ESCAPE '\';
```

---

## IS NULL

```sql
SELECT *
FROM students
WHERE email IS NULL;
```

---

## IS NOT NULL

```sql
SELECT *
FROM students
WHERE email IS NOT NULL;
```

---

## CASE EXPRESSION

```sql
SELECT
    name,
    age,
    CASE
        WHEN age >= 18 THEN 'Adult'
        ELSE 'Minor'
    END AS category
FROM students;
```

---

## Operator Precedence

Use parentheses when expressions become complex:

```sql
SELECT *
FROM students
WHERE age >= 18
  AND (city = 'Lahore' OR city = 'Karachi');
```

---

# 7. Constraints

## Constraints

Common constraints:

```text
PRIMARY KEY
FOREIGN KEY
UNIQUE
CHECK
DEFAULT
NOT NULL
```

---

## UNIQUE Constraint

```sql
CREATE TABLE users (
    id INT,
    email VARCHAR(100) UNIQUE
);
```

---

## PRIMARY KEY

```sql
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(100)
);
```

---

## FOREIGN KEY

```sql
CREATE TABLE orders (
    id INT PRIMARY KEY,
    customer_id INT,
    FOREIGN KEY (customer_id)
        REFERENCES customers(id)
);
```

---

## Candidate Key

A minimal column or combination of columns that can uniquely identify a row.

Example candidates:

```text
student_id
email
national_id
```

---

## Super Key

Any attribute set that uniquely identifies a row.

---

## Alternate Key

A candidate key not selected as the primary key.

---

## CHECK Constraint

```sql
CREATE TABLE students (
    id INT PRIMARY KEY,
    age INT CHECK (age >= 0)
);
```

---

## DEFAULT Constraint

```sql
CREATE TABLE users (
    id INT PRIMARY KEY,
    status VARCHAR(20) DEFAULT 'active'
);
```

---

## Composite Key

```sql
CREATE TABLE enrollments (
    student_id INT,
    course_id INT,
    PRIMARY KEY (student_id, course_id)
);
```

---

## Add Constraint

```sql
ALTER TABLE users
ADD CONSTRAINT unique_email UNIQUE (email);
```

---

## Drop Constraint

Syntax varies by DBMS.

Common form:

```sql
ALTER TABLE users
DROP CONSTRAINT unique_email;
```

---

## Referential Integrity

Foreign keys help maintain relationships between tables.

---

## ON DELETE CASCADE

```sql
FOREIGN KEY (customer_id)
REFERENCES customers(id)
ON DELETE CASCADE
```

---

## ON UPDATE CASCADE

```sql
FOREIGN KEY (customer_id)
REFERENCES customers(id)
ON UPDATE CASCADE
```

---

# 8. Aggregate Functions

## COUNT

```sql
SELECT COUNT(*)
FROM students;
```

---

## COUNT DISTINCT

```sql
SELECT COUNT(DISTINCT city)
FROM students;
```

---

## SUM

```sql
SELECT SUM(amount)
FROM payments;
```

---

## AVG

```sql
SELECT AVG(age)
FROM students;
```

---

## MIN

```sql
SELECT MIN(price)
FROM products;
```

---

## MAX

```sql
SELECT MAX(price)
FROM products;
```

---

## GROUP BY

```sql
SELECT
    city,
    COUNT(*) AS total_students
FROM students
GROUP BY city;
```

---

## HAVING

```sql
SELECT
    city,
    COUNT(*) AS total_students
FROM students
GROUP BY city
HAVING COUNT(*) > 5;
```

---

## WHERE vs HAVING

```text
WHERE  → filters rows before grouping
HAVING → filters groups after GROUP BY
```

Example:

```sql
SELECT
    city,
    COUNT(*) AS total
FROM students
WHERE age >= 18
GROUP BY city
HAVING COUNT(*) >= 2;
```

---

# 9. String Functions

## CONCAT

```sql
SELECT CONCAT(first_name, ' ', last_name) AS full_name
FROM users;
```

---

## CHAR_LENGTH

```sql
SELECT CHAR_LENGTH(name)
FROM students;
```

---

## UPPER

```sql
SELECT UPPER(name)
FROM students;
```

---

## LOWER

```sql
SELECT LOWER(name)
FROM students;
```

---

## TRIM

```sql
SELECT TRIM(name)
FROM students;
```

---

## SUBSTRING

```sql
SELECT SUBSTRING(name, 1, 3)
FROM students;
```

---

## REPLACE

```sql
SELECT REPLACE(name, 'Ali', 'Ahmed')
FROM students;
```

---

## POSITION

Standards-style:

```sql
SELECT POSITION('SQL' IN 'Learn SQL');
```

---

# 10. Numeric Functions

## ABS

```sql
SELECT ABS(-25);
```

---

## ROUND

```sql
SELECT ROUND(12.345, 2);
```

---

## MOD

```sql
SELECT MOD(10, 3);
```

---

## POWER

```sql
SELECT POWER(2, 3);
```

---

## SQRT

```sql
SELECT SQRT(25);
```

---

# 11. Date Functions

## CURRENT_DATE

```sql
SELECT CURRENT_DATE;
```

---

## CURRENT_TIME

```sql
SELECT CURRENT_TIME;
```

---

## CURRENT_TIMESTAMP

```sql
SELECT CURRENT_TIMESTAMP;
```

---

## EXTRACT

```sql
SELECT EXTRACT(YEAR FROM CURRENT_DATE);
```

---

# 12. NULL Functions

## COALESCE

Return the first non-NULL value:

```sql
SELECT COALESCE(phone, email, 'No contact')
FROM users;
```

---

## NULLIF

Returns `NULL` when two values are equal:

```sql
SELECT NULLIF(10, 10);
```

---

# 13. SQL Join

Assume:

```text
customers
---------
id
name

orders
------
id
customer_id
amount
```

---

## INNER JOIN

```sql
SELECT
    customers.name,
    orders.amount
FROM customers
INNER JOIN orders
    ON customers.id = orders.customer_id;
```

---

## LEFT JOIN

```sql
SELECT
    customers.name,
    orders.amount
FROM customers
LEFT JOIN orders
    ON customers.id = orders.customer_id;
```

---

## RIGHT JOIN

Where supported:

```sql
SELECT
    customers.name,
    orders.amount
FROM customers
RIGHT JOIN orders
    ON customers.id = orders.customer_id;
```

---

## FULL OUTER JOIN

Where supported:

```sql
SELECT
    customers.name,
    orders.amount
FROM customers
FULL OUTER JOIN orders
    ON customers.id = orders.customer_id;
```

---

## CROSS JOIN

```sql
SELECT *
FROM colors
CROSS JOIN sizes;
```

---

## SELF JOIN

```sql
SELECT
    e.name AS employee,
    m.name AS manager
FROM employees AS e
LEFT JOIN employees AS m
    ON e.manager_id = m.id;
```

---

## Multiple Joins

```sql
SELECT
    students.name,
    courses.title,
    departments.name
FROM enrollments
JOIN students
    ON enrollments.student_id = students.id
JOIN courses
    ON enrollments.course_id = courses.id
JOIN departments
    ON courses.department_id = departments.id;
```

---

## JOIN with WHERE

```sql
SELECT *
FROM customers
JOIN orders
    ON customers.id = orders.customer_id
WHERE orders.amount > 1000;
```

---

## JOIN with GROUP BY

```sql
SELECT
    customers.name,
    SUM(orders.amount) AS total_spent
FROM customers
JOIN orders
    ON customers.id = orders.customer_id
GROUP BY customers.id, customers.name;
```

---

## UNION

```sql
SELECT email FROM customers
UNION
SELECT email FROM suppliers;
```

Removes duplicates.

---

## UNION ALL

```sql
SELECT email FROM customers
UNION ALL
SELECT email FROM suppliers;
```

Keeps duplicates.

---

## JOIN vs UNION

```text
JOIN  → combines columns from related tables
UNION → combines rows from compatible queries
```

---

## INTERSECT

Where supported:

```sql
SELECT email FROM customers
INTERSECT
SELECT email FROM subscribers;
```

---

## EXCEPT

Where supported:

```sql
SELECT email FROM customers
EXCEPT
SELECT email FROM blocked_users;
```

---

# 14. SQL Subquery

## Basic Subquery

```sql
SELECT *
FROM products
WHERE price > (
    SELECT AVG(price)
    FROM products
);
```

---

## Single Row Subquery

```sql
SELECT *
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);
```

---

## Multiple Row Subquery

```sql
SELECT *
FROM students
WHERE course_id IN (
    SELECT id
    FROM courses
    WHERE department_id = 1
);
```

---

## Nested Subquery

```sql
SELECT *
FROM products
WHERE category_id IN (
    SELECT id
    FROM categories
    WHERE department_id IN (
        SELECT id
        FROM departments
        WHERE active = 1
    )
);
```

---

## Correlated Subquery

```sql
SELECT e1.name, e1.salary
FROM employees AS e1
WHERE e1.salary > (
    SELECT AVG(e2.salary)
    FROM employees AS e2
    WHERE e2.department_id = e1.department_id
);
```

---

## Subquery in SELECT

```sql
SELECT
    name,
    (
        SELECT COUNT(*)
        FROM orders
        WHERE orders.customer_id = customers.id
    ) AS order_count
FROM customers;
```

---

## Subquery in WHERE

```sql
SELECT *
FROM products
WHERE category_id IN (
    SELECT id
    FROM categories
);
```

---

## Subquery in FROM

```sql
SELECT category, average_price
FROM (
    SELECT
        category,
        AVG(price) AS average_price
    FROM products
    GROUP BY category
) AS summary;
```

---

## EXISTS

```sql
SELECT *
FROM customers AS c
WHERE EXISTS (
    SELECT 1
    FROM orders AS o
    WHERE o.customer_id = c.id
);
```

---

## NOT EXISTS

```sql
SELECT *
FROM customers AS c
WHERE NOT EXISTS (
    SELECT 1
    FROM orders AS o
    WHERE o.customer_id = c.id
);
```

---

## ANY

Where supported:

```sql
SELECT *
FROM products
WHERE price > ANY (
    SELECT price
    FROM competitor_products
);
```

---

## ALL

```sql
SELECT *
FROM products
WHERE price > ALL (
    SELECT price
    FROM competitor_products
);
```

---

## IN vs EXISTS

```text
IN     → compares a value against a returned set
EXISTS → checks whether matching rows exist
```

---

## Subquery vs JOIN

```text
Subquery → nested query
JOIN     → combines related tables directly
```

Choose based on clarity, logic, and database optimizer behavior.

---

# 15. SQL Views

## View

A view stores a query definition.

---

## CREATE VIEW

```sql
CREATE VIEW adult_students AS
SELECT id, name, age
FROM students
WHERE age >= 18;
```

---

## Query View

```sql
SELECT *
FROM adult_students;
```

---

## DROP VIEW

```sql
DROP VIEW adult_students;
```

---

# 16. SQL Indexes

## Index

Indexes can improve lookup performance for suitable queries.

---

## CREATE INDEX

```sql
CREATE INDEX idx_students_name
ON students(name);
```

---

## Unique Index

```sql
CREATE UNIQUE INDEX idx_users_email
ON users(email);
```

---

## Composite Index

```sql
CREATE INDEX idx_orders_customer_date
ON orders(customer_id, order_date);
```

---

## DROP INDEX

Syntax varies by DBMS.

Example:

```sql
DROP INDEX idx_students_name;
```

---

## Index Advantages

Potential benefits:

```text
Faster searches
Faster filtering
Faster joins in suitable cases
Faster ordering in suitable cases
```

Indexes also require storage and can add write overhead.

---

# 17. Advanced SQL

## CTE

```sql
WITH high_value_orders AS (
    SELECT *
    FROM orders
    WHERE amount > 1000
)
SELECT *
FROM high_value_orders;
```

---

## Multiple CTEs

```sql
WITH
customers_summary AS (
    SELECT customer_id, COUNT(*) AS order_count
    FROM orders
    GROUP BY customer_id
),
payment_summary AS (
    SELECT customer_id, SUM(amount) AS total_paid
    FROM payments
    GROUP BY customer_id
)
SELECT *
FROM customers_summary
JOIN payment_summary
    USING (customer_id);
```

---

## Recursive CTE

Typical hierarchy pattern:

```sql
WITH RECURSIVE employee_tree AS (
    SELECT id, name, manager_id, 1 AS level
    FROM employees
    WHERE manager_id IS NULL

    UNION ALL

    SELECT
        e.id,
        e.name,
        e.manager_id,
        et.level + 1
    FROM employees AS e
    JOIN employee_tree AS et
        ON e.manager_id = et.id
)
SELECT *
FROM employee_tree;
```

Syntax/support may vary.

---

## WITH Clause

```sql
WITH active_users AS (
    SELECT *
    FROM users
    WHERE status = 'active'
)
SELECT *
FROM active_users;
```

---

## OVER Clause

```sql
SELECT
    name,
    salary,
    AVG(salary) OVER () AS average_salary
FROM employees;
```

---

## Window Functions

```sql
SELECT
    name,
    department_id,
    salary,
    AVG(salary) OVER (
        PARTITION BY department_id
    ) AS department_average
FROM employees;
```

---

## PARTITION BY

```sql
SELECT
    department_id,
    name,
    salary,
    SUM(salary) OVER (
        PARTITION BY department_id
    ) AS department_total
FROM employees;
```

---

## ROW_NUMBER

```sql
SELECT
    name,
    salary,
    ROW_NUMBER() OVER (
        ORDER BY salary DESC
    ) AS row_num
FROM employees;
```

---

## RANK

```sql
SELECT
    name,
    salary,
    RANK() OVER (
        ORDER BY salary DESC
    ) AS salary_rank
FROM employees;
```

---

## DENSE_RANK

```sql
SELECT
    name,
    salary,
    DENSE_RANK() OVER (
        ORDER BY salary DESC
    ) AS salary_rank
FROM employees;
```

---

## NTILE

```sql
SELECT
    name,
    salary,
    NTILE(4) OVER (
        ORDER BY salary DESC
    ) AS salary_group
FROM employees;
```

---

## LAG

```sql
SELECT
    order_date,
    amount,
    LAG(amount) OVER (
        ORDER BY order_date
    ) AS previous_amount
FROM orders;
```

---

## LEAD

```sql
SELECT
    order_date,
    amount,
    LEAD(amount) OVER (
        ORDER BY order_date
    ) AS next_amount
FROM orders;
```

---

## FIRST_VALUE

```sql
SELECT
    name,
    salary,
    FIRST_VALUE(name) OVER (
        ORDER BY salary DESC
    ) AS highest_paid_employee
FROM employees;
```

---

## LAST_VALUE

Window frames matter for `LAST_VALUE`.

Example:

```sql
SELECT
    name,
    salary,
    LAST_VALUE(name) OVER (
        ORDER BY salary
        ROWS BETWEEN UNBOUNDED PRECEDING
        AND UNBOUNDED FOLLOWING
    ) AS highest_paid_employee
FROM employees;
```

---

## Running Total

```sql
SELECT
    order_date,
    amount,
    SUM(amount) OVER (
        ORDER BY order_date
    ) AS running_total
FROM orders;
```

---

## Moving Average

```sql
SELECT
    order_date,
    amount,
    AVG(amount) OVER (
        ORDER BY order_date
        ROWS BETWEEN 2 PRECEDING AND CURRENT ROW
    ) AS moving_average
FROM orders;
```

---

## Conditional Aggregation

```sql
SELECT
    COUNT(
        CASE
            WHEN status = 'completed'
            THEN 1
        END
    ) AS completed_orders
FROM orders;
```

Another common form:

```sql
SELECT
    SUM(
        CASE
            WHEN status = 'completed'
            THEN amount
            ELSE 0
        END
    ) AS completed_total
FROM orders;
```

---

## Top N Per Group

```sql
WITH ranked_employees AS (
    SELECT
        name,
        department_id,
        salary,
        ROW_NUMBER() OVER (
            PARTITION BY department_id
            ORDER BY salary DESC
        ) AS row_num
    FROM employees
)
SELECT *
FROM ranked_employees
WHERE row_num <= 3;
```

---

# 18. SQL Transaction

## Transaction

Typical pattern:

```sql
BEGIN;

UPDATE accounts
SET balance = balance - 500
WHERE id = 1;

UPDATE accounts
SET balance = balance + 500
WHERE id = 2;

COMMIT;
```

Start syntax may differ by DBMS.

---

## ACID Properties

```text
Atomicity
Consistency
Isolation
Durability
```

---

## COMMIT

```sql
COMMIT;
```

Makes transaction changes permanent.

---

## ROLLBACK

```sql
ROLLBACK;
```

Reverses uncommitted changes.

---

## SAVEPOINT

```sql
SAVEPOINT before_update;

UPDATE products
SET price = price * 1.10;

ROLLBACK TO SAVEPOINT before_update;
```

Syntax varies.

---

## Transaction Example

```sql
BEGIN;

INSERT INTO payments (customer_id, amount)
VALUES (1, 500);

UPDATE accounts
SET balance = balance - 500
WHERE customer_id = 1;

COMMIT;
```

---

# 19. Database Design

## Entities

Examples:

```text
Student
Course
Customer
Product
Order
Employee
```

---

## Attributes

Example:

```text
Student
├── student_id
├── name
├── email
└── age
```

---

## Relationships

Examples:

```text
Customer → Orders
Student → Courses
Department → Employees
```

---

## ER Diagram

Simple relationship:

```text
CUSTOMER
   |
   | 1
   |
   |----< ORDER
          many
```

---

## Cardinality

Common relationships:

```text
One-to-One
One-to-Many
Many-to-Many
```

---

## Normalization

Normalization organizes relational data to reduce undesirable redundancy
and dependencies.

---

## Functional Dependency

Concept:

```text
A → B
```

means attribute `A` determines attribute `B`.

Example:

```text
student_id → student_name
```

---

## First Normal Form (1NF)

Typical goal:

```text
Atomic values
No repeating groups
```

---

## Second Normal Form (2NF)

Typical concept:

```text
1NF
+
No partial dependency on part of a composite key
```

---

## Third Normal Form (3NF)

Typical concept:

```text
2NF
+
Remove inappropriate transitive dependencies
```

---

## Boyce-Codd Normal Form (BCNF)

Stronger normalization condition related to determinants and candidate keys.

---

## Denormalization

Intentional duplication can sometimes be introduced for specific
performance or reporting needs.

---

# 20. Stored Programs

Stored program syntax varies significantly by DBMS.

## Stored Procedure

MySQL-style example:

```sql
DELIMITER //

CREATE PROCEDURE GetStudents()
BEGIN
    SELECT *
    FROM students;
END //

DELIMITER ;
```

---

## Call Procedure

```sql
CALL GetStudents();
```

---

## Procedure Parameters

Example:

```sql
DELIMITER //

CREATE PROCEDURE GetStudentById(
    IN studentId INT
)
BEGIN
    SELECT *
    FROM students
    WHERE id = studentId;
END //

DELIMITER ;
```

---

## Drop Procedure

```sql
DROP PROCEDURE GetStudents;
```

---

## Stored Function

MySQL-style example:

```sql
DELIMITER //

CREATE FUNCTION AddNumbers(
    a INT,
    b INT
)
RETURNS INT
DETERMINISTIC
BEGIN
    RETURN a + b;
END //

DELIMITER ;
```

---

## Procedure vs Function

```text
Procedure
→ performs an operation
→ may return result sets/output parameters

Function
→ returns a value
→ usage rules depend on DBMS
```

---

# 21. SQL Trigger

Trigger syntax varies by DBMS.

## Create Trigger

MySQL-style example:

```sql
CREATE TRIGGER before_product_insert
BEFORE INSERT ON products
FOR EACH ROW
SET NEW.created_at = CURRENT_TIMESTAMP;
```

---

## BEFORE Trigger

Runs before an event.

Concept:

```sql
BEFORE INSERT
BEFORE UPDATE
BEFORE DELETE
```

---

## AFTER Trigger

Runs after an event.

Concept:

```sql
AFTER INSERT
AFTER UPDATE
AFTER DELETE
```

---

## Drop Trigger

```sql
DROP TRIGGER before_product_insert;
```

---

# 22. SQL Cursor

Cursor syntax is highly DBMS-specific.

General workflow:

```text
DECLARE
↓
OPEN
↓
FETCH
↓
PROCESS
↓
CLOSE
```

---

## Declare Cursor

Conceptual example:

```sql
DECLARE student_cursor CURSOR
FOR
SELECT id, name
FROM students;
```

---

## Fetch Cursor

Concept:

```sql
FETCH NEXT FROM student_cursor;
```

Exact syntax varies.

---

## Close Cursor

Concept:

```sql
CLOSE student_cursor;
```

---

## Move Cursor

Cursor movement capabilities depend on cursor type and DBMS.

---

# 23. SQL Projects

## 🏦 Banking Database

Suggested entities:

```text
customers
accounts
transactions
branches
```

Practice:

```text
Primary keys
Foreign keys
Joins
Transactions
Aggregate functions
Constraints
Indexes
```

---

## 🎓 University Database

Suggested entities:

```text
students
courses
departments
teachers
enrollments
```

Practice:

```text
Relationships
Many-to-many design
Composite keys
Joins
Subqueries
Views
Normalization
```

---

## 🛒 Ecommerce Database

Suggested entities:

```text
customers
products
categories
orders
order_items
payments
inventory
```

Practice:

```text
Joins
Aggregates
Transactions
CTEs
Window functions
Indexes
Database design
```

---

# ⚡ Frequently Used SQL Patterns

## Select Everything

```sql
SELECT *
FROM table_name;
```

---

## Select Specific Columns

```sql
SELECT column1, column2
FROM table_name;
```

---

## Filter

```sql
SELECT *
FROM table_name
WHERE condition;
```

---

## Sort

```sql
SELECT *
FROM table_name
ORDER BY column_name DESC;
```

---

## Group

```sql
SELECT
    category,
    COUNT(*) AS total
FROM products
GROUP BY category;
```

---

## Filter Groups

```sql
SELECT
    category,
    COUNT(*) AS total
FROM products
GROUP BY category
HAVING COUNT(*) > 5;
```

---

## Join Tables

```sql
SELECT *
FROM table_a
JOIN table_b
    ON table_a.id = table_b.a_id;
```

---

## Insert

```sql
INSERT INTO table_name (column1, column2)
VALUES (value1, value2);
```

---

## Update Safely

```sql
UPDATE table_name
SET column_name = value
WHERE id = 1;
```

---

## Delete Safely

```sql
DELETE FROM table_name
WHERE id = 1;
```

---

# 🧠 Core SQL Query Order

A common query structure:

```sql
SELECT
    column1,
    aggregate_function(column2)
FROM table_name
JOIN another_table
    ON condition
WHERE row_condition
GROUP BY column1
HAVING group_condition
ORDER BY column1
LIMIT 10;
```

Conceptual processing flow is different from written syntax,
but this layout is useful when writing many queries.

---

# 🎯 SQL Learning Flow

```text
SQL Fundamentals
      ↓
Database
      ↓
Tables
      ↓
Insert / Update / Delete
      ↓
SELECT
      ↓
Filtering
      ↓
Constraints
      ↓
Functions
      ↓
Joins
      ↓
Subqueries
      ↓
Views
      ↓
Indexes
      ↓
CTEs & Window Functions
      ↓
Transactions
      ↓
Database Design
      ↓
Stored Programs
      ↓
Triggers
      ↓
Cursors
      ↓
Projects
```

---

# 📘 Complete SQL Roadmap

For the complete A1Lab SQL learning sequence:

## [Open the SQL Learning Roadmap →](../roadmaps/sql-roadmap.md)

---

# 🌐 Learn SQL With A1Lab

A1Lab combines:

- 🎓 Structured SQL lessons
- 💻 Interactive learning
- 🧠 Visual explanations
- 🧪 Practical examples
- 📝 Practice activities
- ❓ MCQs and learning checks
- 💬 Developer discussions

<div align="center">

<a href="https://a1lab.tech/sql/introduction">
  <img
    src="https://img.shields.io/badge/Start_SQL_Course-A1Lab-04AA6D?style=for-the-badge&logo=mysql&logoColor=white"
    alt="Start SQL Course on A1Lab"
  />
</a>

<br><br>

## [Explore A1Lab →](https://a1lab.tech)

</div>

---

# 👨‍💻 Maintainer

**Muhammad Ahmad**

Founder & Full-Stack Developer behind
**[A1Lab](https://a1lab.tech)**

GitHub:

[mahmad786-cloud](https://github.com/mahmad786-cloud)

---

<div align="center">

# 🗄️ Learn. Query. Design. Build.

### SQL quick reference from fundamentals to advanced database concepts.

**A1Lab Learning Resources**

### [Start Learning SQL →](https://a1lab.tech/sql/introduction)

</div>
