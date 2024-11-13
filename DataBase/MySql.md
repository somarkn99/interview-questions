# MySQL Technical Interview Questions and Answers

## 1. What is MySQL?

MySQL is an open-source relational database management system (RDBMS) that uses Structured Query Language (SQL) for accessing and managing data. It is widely used for web applications and is known for its reliability, flexibility, and ease of use. MySQL supports various database operations such as data insertion, querying, updating, and deletion while ensuring data integrity.

## 2. What are the different types of joins in MySQL?

In MySQL, joins are used to combine rows from two or more tables based on a related column. The main types of joins include:

- **INNER JOIN**: Returns records that have matching values in both tables.
- **LEFT JOIN** (or LEFT OUTER JOIN): Returns all records from the left table and matched records from the right table. If no match exists, NULL values are returned for columns from the right table.
- **RIGHT JOIN** (or RIGHT OUTER JOIN): Returns all records from the right table and matched records from the left table. If no match exists, NULL values are returned for columns from the left table.
- **FULL OUTER JOIN**: Returns all records when there is a match in either left or right table records. (Note: MySQL does not support FULL OUTER JOIN directly but can be achieved using a combination of LEFT and RIGHT JOIN.)

## 3. What is normalization? Explain its types

Normalization is the process of organizing data in a database to reduce redundancy and improve data integrity. It involves dividing large tables into smaller tables and defining relationships between them. The main types of normalization include:

- **1NF (First Normal Form)**: Ensures that the table has no repeating groups or arrays and that each column contains atomic values.
- **2NF (Second Normal Form)**: Achieves 1NF and ensures that all non-key attributes are fully functional dependent on the primary key.
- **3NF (Third Normal Form)**: Achieves 2NF and removes transitive dependencies, ensuring that non-key attributes are only dependent on the primary key.
- **BCNF (Boyce-Codd Normal Form)**: A stronger version of 3NF, where every determinant is a candidate key.

## 4. How do you create an index in MySQL, and why would you use it?

An index in MySQL can be created using the CREATE INDEX statement, which improves the speed of data retrieval operations on a database table. Indexes work like a lookup table that allows the database engine to find data without scanning the entire table.

Using indexes can significantly enhance query performance, especially for large datasets, but they may slow down data modification operations (INSERT, UPDATE, DELETE) due to the overhead of maintaining the index.

## 5. What are primary keys and foreign keys?

A **primary key** is a unique identifier for each record in a database table. It ensures that no two rows have the same value in the primary key column(s) and cannot contain NULL values. A **foreign key** is a field (or collection of fields) in one table that uniquely identifies a row in another table, establishing a relationship between the two tables.

## 6. What is a stored procedure in MySQL?

A stored procedure is a set of SQL statements that can be stored and executed on the database server. It allows for modular programming, meaning you can write complex operations once and call them whenever needed. Stored procedures can accept parameters, return values, and improve performance by reducing the amount of information sent over the network.

## 7. Explain ACID properties in the context of MySQL

ACID properties ensure reliable processing of database transactions:

- **Atomicity**: Guarantees that all operations within a transaction are completed successfully; if any operation fails, the entire transaction is rolled back.
- **Consistency**: Ensures that a transaction brings the database from one valid state to another valid state, maintaining data integrity.
- **Isolation**: Ensures that concurrent transactions do not interfere with each other; each transaction is executed as if it were the only one running.
- **Durability**: Guarantees that once a transaction has been committed, it will remain so even in the event of a system failure.

## 8. What is a view in MySQL? How does it differ from a table?

A view is a virtual table created by a query that selects data from one or more tables. Unlike a regular table, a view does not store data physically; it dynamically retrieves data when accessed. Views can simplify complex queries, encapsulate business logic, and provide security by restricting access to specific data columns or rows.

## 9. What are triggers in MySQL?

Triggers are automated actions defined to execute in response to specific events on a particular table, such as INSERT, UPDATE, or DELETE operations. They allow for enforcing business rules at the database level without requiring application-level logic.

## 10. How do you optimize a slow query in MySQL?

To optimize slow queries in MySQL, consider the following techniques:

- Create appropriate indexes on columns used in WHERE clauses or JOIN conditions to speed up lookups.
- Avoid using SELECT *; instead, specify only the necessary columns to reduce data transfer.
- Optimize joins by ensuring proper indexing and minimizing the number of rows processed.
- Consider caching results for frequently run queries using caching mechanisms.

## 11. What is the difference between UNION and UNION ALL?

Both UNION and UNION ALL are used to combine results from two or more SELECT queries:

- **UNION**: Combines results from multiple queries and removes duplicate rows from the final result set.
- **UNION ALL**: Combines results from multiple queries without removing duplicates, thus returning all rows from each query.
As a result, UNION ALL is generally faster than UNION because it does not require additional processing to eliminate duplicates.

## 12. How can you prevent SQL injection attacks in MySQL?

SQL injection attacks can be mitigated by following best practices such as:

- Using prepared statements with parameterized queries to separate SQL logic from data input.
- Validating and sanitizing user inputs to ensure they conform to expected formats.
- Utilizing ORM frameworks that automatically handle parameterization and escaping.

## 13. What is replication in MySQL?

Replication in MySQL refers to the process of copying and maintaining database objects (like tables) across multiple servers. The server that sends data is called the master server, while one or more servers that receive data are called slave servers. Replication helps improve data availability, load balancing, and disaster recovery by allowing read operations to be distributed across multiple servers.

## 14. Explain the difference between InnoDB and MyISAM storage engines

InnoDB and MyISAM are two popular storage engines in MySQL:

- **InnoDB**: The default storage engine for MySQL, supports transactions (ACID compliance), foreign keys, row-level locking for better concurrency, and crash recovery features. It is suitable for applications requiring high reliability and data integrity.
- **MyISAM**: Does not support transactions or foreign keys but offers faster read operations due to table-level locking. It is suitable for read-heavy workloads where speed is prioritized over strict data integrity.
