✅ 100 SQL Theory Questions with Answers
1. **What is SQL?**
   - SQL (Structured Query Language) is a standard language for accessing and manipulating databases.

2. **What are the different types of SQL statements?**
   - DDL (Data Definition Language), DML (Data Manipulation Language), DCL (Data Control Language), TCL (Transaction Control Language).

3. **What is a primary key?**
   - A field (or combination) that uniquely identifies each record in a table.

4. **What is a foreign key?**
   - A key used to link two tables. It refers to the primary key in another table.

5. **What is a unique key?**
   - Ensures all values in a column are different but allows one NULL value.

6. **What is the difference between WHERE and HAVING?**
   - WHERE filters rows before grouping; HAVING filters groups after aggregation.

7. **What is normalization?**
   - A technique to reduce redundancy and dependency by organizing fields and tables.

8. **What is denormalization?**
   - Process of combining tables to improve read performance.

9. **What are joins in SQL?**
   - Joins combine rows from two or more tables based on a related column.

10. **Types of joins?**
   - INNER, LEFT, RIGHT, FULL OUTER JOIN.

11. **What is a view?**
   - A virtual table based on the result of an SQL query.

12. **What is an index?**
   - A database object to improve the speed of data retrieval.

13. **What is a clustered index?**
   - Sorts and stores data rows in the table based on key values.

14. **What is a non-clustered index?**
   - A separate structure that points to the location of data in the table.

15. **What is the difference between DELETE and TRUNCATE?**
   - DELETE removes rows one by one with logging; TRUNCATE removes all rows quickly without logging.

16. **What is the difference between DROP and DELETE?**
   - DROP removes the table; DELETE removes the rows.

17. **What is a subquery?**
   - A query nested inside another query.

18. **What is a correlated subquery?**
   - A subquery that references columns from the outer query.

19. **What are transactions?**
   - A set of SQL operations performed as a single logical unit.

20. **What are ACID properties?**
   - Atomicity, Consistency, Isolation, Durability.

What is a constraint in SQL?
A constraint is used to specify rules for data in a table (e.g., NOT NULL, UNIQUE, CHECK, DEFAULT, PRIMARY KEY).

What is the CHECK constraint?
It ensures that values in a column meet a specific condition.

What is the DEFAULT constraint?
It provides a default value for a column when no value is specified.

What is the NOT NULL constraint?
Ensures a column cannot have a NULL value.

What is the UNIQUE constraint?
Ensures all values in a column are different.

What is a surrogate key?
A system-generated primary key (like an auto-incremented number) used to uniquely identify a record.

What is the difference between CHAR and VARCHAR?
CHAR is fixed-length; VARCHAR is variable-length.

What is a NULL value?
Represents missing or unknown data.

What is a self join?
A self join is a regular join where a table is joined with itself.

What is a cross join?
Produces a Cartesian product of rows from two tables.

What is the purpose of the COALESCE function?
Returns the first non-null value in a list.

What is the ISNULL() function?
Replaces NULL with the specified replacement value.

What are stored procedures?
A stored procedure is a saved collection of SQL statements that can be executed repeatedly.

What is a function in SQL?
A function performs a task and returns a value. It can be used in SQL expressions.

What is the difference between function and procedure?
A function returns a value and can be used in queries; a procedure can perform actions but may not return a value directly.

What is a trigger?
A trigger is a set of instructions that automatically execute in response to certain events on a table.

What is a cursor in SQL?
A cursor is used to retrieve and manipulate data row-by-row.

What is the difference between static and dynamic SQL?
Static SQL is compiled before execution, dynamic SQL is compiled at runtime.

What is a composite key?
A primary key consisting of more than one column.

What is the BETWEEN operator?
Filters the result set within a specified range (inclusive).

What is the IN operator used for?
Checks if a value matches any value in a list or subquery.

What is the LIKE operator used for?
Performs pattern matching on string data.

What are aggregate functions in SQL?
Functions like SUM(), AVG(), MIN(), MAX(), COUNT() that operate on sets of values.

What is the LIMIT clause?
Restricts the number of rows returned.

What is the OFFSET clause?
Skips a specified number of rows before beginning to return rows.

What is normalization’s main goal?
To eliminate redundant data and ensure data dependencies make sense.

What is 1NF (First Normal Form)?
Ensures all columns contain atomic values and each column contains only one value per row.

What is 2NF (Second Normal Form)?
A table is in 2NF if it is in 1NF and all non-key columns are fully functionally dependent on the primary key.

What is 3NF (Third Normal Form)?
A table is in 3NF if it is in 2NF and all columns are only dependent on the primary key.

What is BCNF (Boyce-Codd Normal Form)?
A stronger version of 3NF where every determinant is a candidate key.

What is an alias in SQL?
A temporary name given to a table or column for readability.

What is a scalar function?
Operates on a single value and returns a single value (e.g., UCASE(), LCASE()).

What is a table-valued function?
Returns a table as output instead of a single value.

What is CASE in SQL?
SQL's way of handling conditional logic (similar to if-else).

What is the use of the EXPLAIN keyword?
Provides the execution plan of a query, useful for optimization.

What is the difference between INNER JOIN and OUTER JOIN?
INNER JOIN returns matched rows; OUTER JOIN returns matched and unmatched rows.

What are temporary tables?
Tables that are created and used during a session and are deleted when the session ends.

What are materialized views?
Stored query results that can be refreshed periodically.

What is the difference between a view and a materialized view?
A view is virtual; a materialized view is stored on disk and can improve performance.

What is recursive SQL?
SQL that calls itself repeatedly, often used with CTEs (Common Table Expressions).

What is a CTE (Common Table Expression)?
A temporary result set used within a query.

What is the ROW_NUMBER() function?
Assigns a unique row number to each row within a result set.

What is PARTITION BY used for?
Divides result sets into partitions to apply window functions.

What is a window function?
Performs calculations across a set of rows related to the current row.

What is a transaction log?
A record of all transactions and changes made to the database.

What is savepoint in SQL?
Marks a point within a transaction to which you can later roll back.

What is rollback in SQL?
Undoes changes made in the current transaction.

What is commit in SQL?
Saves all changes made in the current transaction.

What is an exception in SQL?
An error condition that interrupts query execution.

What are system tables?
Tables maintained by the database engine for internal use.

What is query optimization?
Improving query performance by rewriting or restructuring queries.

What is a deadlock in SQL?
A situation where two transactions block each other by holding locks.

What is data integrity?
Ensuring accuracy and consistency of data over its lifecycle.

What are synonyms in SQL?
Alternative names for database objects.

What is the purpose of the SET keyword?
Used to assign values to variables or update columns.

What are global variables in SQL?
Variables defined at the system level that apply to all sessions.

What is an execution plan?
Describes how SQL Server executes a query, step-by-step.

What is horizontal vs vertical partitioning?
Horizontal splits rows, vertical splits columns across tables or databases.

What is data replication?
Copying data from one database to another for backup or availability.

What is sharding?
Breaking a large database into smaller parts (shards) for performance/scalability.

What is ETL?
Extract, Transform, Load – used to move and process data between systems.

What is OLAP?
Online Analytical Processing – used for complex queries and data analysis.

What is OLTP?
Online Transaction Processing – used for transaction-based applications.

What is data warehousing?
The storage of large volumes of historical data for analysis.

What is referential integrity?
Ensures foreign keys correctly and consistently reference valid rows.

What is surrogate key vs natural key?
Surrogate key is artificially generated; natural key is a real-world unique identifier.

What is schema vs database?
A schema is a logical collection of tables; a database contains one or more schemas.

What is JSON in SQL?
SQL Server and others support storing and querying JSON-formatted data.

What is XML in SQL?
SQL supports storing, parsing, and querying XML documents.

What is an execution context?
The environment under which a query is executed (permissions, roles).

What is column aliasing?
Renaming a column in the output for readability.

What is table aliasing?
Giving a short name to a table in a query.

What is the purpose of SQL Profiler?
A tool used to monitor and trace SQL Server activity.

What is indexing strategy?
Planning how indexes are used to optimize performance.

What is a heap table?
A table without a clustered index.

What is fill factor in indexing?
Determines how full index pages are when created.

What is a covering index?
An index that includes all columns needed by a query.

What is data archiving?
Moving old data out of active systems for storage and compliance.

What is log shipping?
Copying transaction logs from one server to another for backup.

What is database mirroring?
Keeping a real-time copy of the database on another server.

What is ETL?
Extract, Transform, Load – used to move and process data between systems.

What is OLAP?
Online Analytical Processing – used for complex queries and data analysis.

What is OLTP?
Online Transaction Processing – used for transaction-based applications.

What is data warehousing?
The storage of large volumes of historical data for analysis.

What is referential integrity?
Ensures foreign keys correctly and consistently reference valid rows.

What is surrogate key vs natural key?
Surrogate key is artificially generated; natural key is a real-world unique identifier.

What is schema vs database?
A schema is a logical collection of tables; a database contains one or more schemas.

What is JSON in SQL?
SQL Server and others support storing and querying JSON-formatted data.

What is XML in SQL?
SQL supports storing, parsing, and querying XML documents.

What is an execution context?
The environment under which a query is executed (permissions, roles).

What is column aliasing?
Renaming a column in the output for readability.

What is table aliasing?
Giving a short name to a table in a query.

What is the purpose of SQL Profiler?
A tool used to monitor and trace SQL Server activity.

What is indexing strategy?
Planning how indexes are used to optimize performance.

What is a heap table?
A table without a clustered index.

What is fill factor in indexing?
Determines how full index pages are when created.

What is a covering index?
An index that includes all columns needed by a query.

What is data archiving?
Moving old data out of active systems for storage and compliance.

What is log shipping?
Copying transaction logs from one server to another for backup.

What is database mirroring?
Keeping a real-time copy of the database on another server.

What is ETL?
Extract, Transform, Load – used to move and process data between systems.

What is OLAP?
Online Analytical Processing – used for complex queries and data analysis.

What is OLTP?
Online Transaction Processing – used for transaction-based applications.

What is data warehousing?
The storage of large volumes of historical data for analysis.

What is referential integrity?
Ensures foreign keys correctly and consistently reference valid rows.

What is surrogate key vs natural key?
Surrogate key is artificially generated; natural key is a real-world unique identifier.

What is schema vs database?
A schema is a logical collection of tables; a database contains one or more schemas.

What is JSON in SQL?
SQL Server and others support storing and querying JSON-formatted data.

What is XML in SQL?
SQL supports storing, parsing, and querying XML documents.

What is an execution context?
The environment under which a query is executed (permissions, roles).

What is column aliasing?
Renaming a column in the output for readability.

What is table aliasing?
Giving a short name to a table in a query.

What is the purpose of SQL Profiler?
A tool used to monitor and trace SQL Server activity.

What is indexing strategy?
Planning how indexes are used to optimize performance.

What is a heap table?
A table without a clustered index.

What is fill factor in indexing?
Determines how full index pages are when created.

What is a covering index?
An index that includes all columns needed by a query.

What is data archiving?
Moving old data out of active systems for storage and compliance.

What is log shipping?
Copying transaction logs from one server to another for backup.

What is database mirroring?
Keeping a real-time copy of the database on another server.

