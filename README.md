# essential-sql-queries
A collection of essential SQL queries for data analysis, covering data retrieval, filtering, aggregation, joins, window functions, and best practices. Ideal for data analysts looking to enhance their SQL skills with practical examples and real-world use cases.

Essential SQL Queries for Data Analysis

Learn the most important SQL queries every data analyst should know to extract, manipulate, and analyze data efficiently.

Introduction
	•	Briefly introduce SQL and why it’s crucial for data analysts.
	•	Mention common use cases (e.g., retrieving data, cleaning datasets, generating reports).
	•	Highlight that this article will cover essential queries with practical examples.

1. Selecting Data: SELECT Statement
	•	Syntax:

SELECT column1, column2 FROM table_name;


	•	Example: Retrieving all customer names and emails from a sales table.

2. Filtering Data: WHERE Clause
	•	How to filter records using conditions:

SELECT * FROM orders WHERE order_date >= '2024-01-01';


	•	Using operators like =, !=, <, >, LIKE, and IN.

3. Sorting Results: ORDER BY Clause
	•	How to sort data in ascending or descending order:

SELECT * FROM products ORDER BY price DESC;



4. Aggregating Data: GROUP BY and HAVING
	•	Summarizing data with COUNT, SUM, AVG, MIN, and MAX:

SELECT category, COUNT(*) AS total_products 
FROM products 
GROUP BY category;


	•	Filtering grouped results with HAVING:

SELECT department, AVG(salary) 
FROM employees 
GROUP BY department 
HAVING AVG(salary) > 50000;



5. Joining Tables: JOIN Operations
	•	Understanding different types of joins (INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL JOIN).
	•	Example: Retrieving customer orders by joining customers and orders tables:

SELECT customers.name, orders.order_id, orders.amount 
FROM customers 
INNER JOIN orders ON customers.customer_id = orders.customer_id;



6. Using Subqueries for Complex Analysis
	•	How to use subqueries to filter results:

SELECT name, salary 
FROM employees 
WHERE salary > (SELECT AVG(salary) FROM employees);


	•	When to use subqueries instead of joins.

7. Window Functions for Advanced Analysis
	•	Using RANK(), DENSE_RANK(), and ROW_NUMBER() for ranking:

SELECT name, department, salary, 
       RANK() OVER (PARTITION BY department ORDER BY salary DESC) AS rank
FROM employees;


	•	How LEAD() and LAG() help in time-series analysis.

8. Common Table Expressions (CTEs) for Readability
	•	How CTEs improve query organization:

WITH high_salary AS (
    SELECT name, salary FROM employees WHERE salary > 70000
)
SELECT * FROM high_salary;



Conclusion
	•	Recap the key queries covered.
	•	Encourage practicing these queries using sample datasets.
	•	Suggest next steps (e.g., learning indexing, query optimization).

Additional Resources
	•	Links to SQL documentation, online courses, and practice platforms like LeetCode SQL, Mode Analytics, or W3Schools.
	•	Example GitHub repo with SQL scripts for hands-on
