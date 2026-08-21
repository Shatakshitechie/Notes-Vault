# SQL Syllabus

A structured path from beginner to advanced SQL.

## 1. Introduction to SQL & Databases
- What is Data (types, preprocessing)
- What is a Database (why we need it, types: relational vs non-relational)
- Database Management (storage, retrieval, update, security, backup)
- DBMS (types, RDBMS, DBMS vs RDBMS)
- MySQL (key features, setup)

## 2. Basic Queries
- `SELECT`, `FROM`, `WHERE`
- `DISTINCT`
- `ORDER BY`, `LIMIT` / `TOP`
- Comparison & logical operators (`=`, `<>`, `AND`, `OR`, `NOT`, `BETWEEN`, `IN`, `LIKE`)
- `NULL` handling (`IS NULL`, `IS NOT NULL`)

## 3. Filtering & Aggregation
- Aggregate functions: `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`
- `GROUP BY`
- `HAVING` vs `WHERE`
- Basic string functions (`CONCAT`, `SUBSTRING`, `UPPER`/`LOWER`, `TRIM`)
- Date functions (`NOW()`, `DATEDIFF`, `EXTRACT`)

## 4. Joins
- `INNER JOIN`
- `LEFT JOIN` / `RIGHT JOIN`
- `FULL OUTER JOIN`
- `CROSS JOIN`
- Self joins
- Multiple table joins

## 5. Data Definition & Manipulation (DDL/DML)
- `CREATE TABLE`, `ALTER TABLE`, `DROP TABLE`
- Data types (INT, VARCHAR, DATE, BOOLEAN, etc.)
- Constraints: `PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE`, `NOT NULL`, `DEFAULT`, `CHECK`
- `INSERT`, `UPDATE`, `DELETE`
- `TRUNCATE` vs `DELETE` vs `DROP`

## 6. Subqueries & Set Operations
- Subqueries (scalar, correlated, nested)
- `ANY`, `ALL`
- `UNION`, `UNION ALL`
- `INTERSECT`, `EXCEPT`/`MINUS`

## 7. Advanced Querying
- Common Table Expressions (`WITH` / CTEs)
- Recursive CTEs
- Window functions (`ROW_NUMBER`, `RANK`, `DENSE_RANK`, `NTILE`)
- Window aggregates (`SUM() OVER`, `AVG() OVER`, partitioning)
- `LEAD`, `LAG`
- `CASE WHEN` statements

## 8. Database Design & Normalization
- ER diagrams, relationships (1:1, 1:N, N:N)
- Normalization (1NF, 2NF, 3NF, BCNF)
- Denormalization trade-offs
- Indexing (types, when to use)

## 9. Views, Procedures & Functions
- Creating/using `VIEW`s
- Stored procedures
- User-defined functions
- Triggers

## 10. Transactions & Concurrency
- `COMMIT`, `ROLLBACK`, `SAVEPOINT`
- ACID properties
- Isolation levels
- Locking basics

## 11. Performance & Optimization
- Query execution plans (`EXPLAIN`)
- Index optimization
- Query optimization techniques
- Avoiding N+1 queries, denormalization when needed

## 12. Advanced Topics
- JSON functions in SQL
- Pivoting/unpivoting data
- Partitioning tables
- Working with large datasets
- SQL in Python (using `sqlite3`, `SQLAlchemy`, `pandas.read_sql`)

## 13. Practice & Real-World Application
- Writing complex analytical queries
- Case studies / practice problem sets (LeetCode SQL, HackerRank SQL)
- Connecting SQL to a GenAI/data pipeline
