Database Fundamentals
Q1. What is a Database?
Answer:

A database is an organized collection of data that can be easily stored, accessed, managed, and updated.

Example:

A university database stores information about students, courses, instructors, and grades.

Q2. What is a DBMS?
Answer:

A DBMS stands for Database Management System.

It is software that allows users to create, store, retrieve, update, and manage data in a database.

Examples: SQL Server, MySQL, Oracle, and PostgreSQL.

Q3. What is the difference between DBMS and RDBMS?
Answer:

A DBMS is a general system used to manage data.

An RDBMS is a type of DBMS that organizes data into tables and establishes relationships between them using keys.

Example:

SQL Server is an RDBMS because it stores data in related tables.

Q4. Why do we use a DBMS instead of storing data in files?
Answer:

A DBMS provides better data management, security, consistency, and data integrity.

It also supports multiple users accessing and modifying data simultaneously.

Example:

Instead of storing customer information in multiple Excel files, we can store it in related database tables.

Q5. What is a Database Schema?
Answer:

A database schema is the logical structure of a database.

It defines tables, columns, data types, relationships, and constraints.

Example:

An Employee table may contain EmployeeID, FirstName, Salary, and DepartmentID.

Q6. What is the difference between Schema and Database Instance?
Answer:

A schema defines the structure of a database, while an instance represents the actual data stored in the database at a specific moment.

Example:

The Employee table structure is part of the schema.

The employees stored inside that table represent the database instance.

Q7. What are Data Redundancy and Data Inconsistency?
Answer:

Data redundancy means storing the same information multiple times.

Data inconsistency happens when duplicated information has different values in different places.

Example:

If a customer's address is stored in five different records, updating only four of them creates inconsistent data.

Q8. What is Data Integrity?
Answer:

Data integrity means maintaining accurate, valid, and consistent data throughout its lifecycle.

We can enforce data integrity using constraints such as Primary Key, Foreign Key, Unique, and Check constraints.

Q9. What is an Entity Relationship Model?
Answer:

An Entity Relationship Model is a conceptual representation of the data and the relationships between entities.

It helps us understand the database requirements before creating actual tables.

Example:

A university system may contain Students, Courses, and Departments.

Q10. What is Cardinality?
Answer:

Cardinality defines how many records of one entity can be associated with records of another entity.

There are three main relationship types:
- One-to-One (1:1)
- One-to-Many (1:M)
- Many-to-Many (M:N)
Example:

One Department can have many Employees. This is a One-to-Many relationship.

systemdesign.academy+1


Section 2 — Keys and Constraints

دي من أهم أجزاء الانترفيو، ولازم تكون قادر تشرحها بمثال من تصميم قاعدة بيانات، مش مجرد تعريف محفوظ.
Q11. What is a Primary Key?
Answer:

A Primary Key is a column, or a combination of columns, that uniquely identifies each row in a table.

It cannot contain NULL values or duplicate values.

Example:

EmployeeID in an Employee table.

Q12. What is a Foreign Key?
Answer:

A Foreign Key is a column that creates a relationship between two tables.

It references a Primary Key or a suitable Unique Key in another table and maintains referential integrity.

Example:

CustomerID in the Orders table references CustomerID in the Customers table.

Q13. What is the difference between Primary Key and Foreign Key?
Answer:

A Primary Key uniquely identifies each row within its own table.

A Foreign Key references a key in another table to establish a relationship between tables.

Q14. What is a UNIQUE Constraint?
Answer:

A UNIQUE constraint ensures that duplicate values cannot be inserted into a column or combination of columns.

Unlike a Primary Key, a table can have multiple UNIQUE constraints.

Q15. What is the difference between PRIMARY KEY and UNIQUE?
Answer:

Both enforce uniqueness.

However, a table can have only one Primary Key, while it can have multiple UNIQUE constraints.

A Primary Key cannot contain NULL values.

Q16. What is a Composite Primary Key?
Answer:

A Composite Primary Key consists of two or more columns used together to uniquely identify a record.

Example:

In an Enrollment table, we can use StudentID and CourseID together as a Composite Primary Key.

Neither column necessarily needs to be unique by itself, but their combination must be unique.

Q17. What are Candidate Key and Super Key?
Answer:

A Super Key is any combination of columns that uniquely identifies a row.

A Candidate Key is a minimal Super Key, meaning no unnecessary column can be removed while maintaining uniqueness.

The Primary Key is selected from the Candidate Keys.
Q18. What is the difference between NOT NULL and CHECK Constraints?
Answer:

NOT NULL prevents a column from storing NULL values.

CHECK validates whether a value satisfies a specific condition.

Example:
Salary DECIMAL(10,2) NOT NULL,
CHECK (Salary > 0)


This means Salary must have a value greater than zero.

Q19. What is a DEFAULT Constraint?
Answer:

A DEFAULT constraint automatically provides a predefined value when no value is supplied for a column.

Example:
StockQuantity INT DEFAULT 0


When an INSERT statement omits StockQuantity, SQL Server uses zero, provided the column is not explicitly given another value.

Q20. What is the purpose of a Foreign Key?
Answer:

A Foreign Key maintains referential integrity between related tables.

It prevents inserting a reference to a parent record that does not exist, and normally prevents deleting a referenced parent record while child records still depend on it.

Microsoft Learn+1

Section 3 — Normalization and Database Design

دي منطقة مهمة جدًا بالنسبالك؛ لأنها بتختبر هل تقدر تصمم Database صح، مش بس تكتب SQL.
Q21. What is Database Normalization?
Answer:

Normalization is the process of organizing data into multiple related tables to reduce data redundancy and avoid data anomalies.

The main goal is to maintain data consistency and improve database design.
Q22. What are Data Anomalies?
Answer:

Data anomalies are problems that occur when data is poorly organized or duplicated.

There are three main types:
1. Insertion Anomaly: We cannot insert certain information without inserting unrelated information.
2. Update Anomaly: We need to update the same information in multiple places.
3. Deletion Anomaly: Deleting one record accidentally removes other important information.
4. 
Q23. What is First Normal Form (1NF)?
Answer:

A table is in First Normal Form when every column contains atomic values, and there are no repeating groups or multiple values in a single cell.

Example:

Incorrect:
StudentID	PhoneNumbers
1	0100, 0110

Correct: Store phone numbers as separate records in an appropriate related table.

Q24. What is Second Normal Form (2NF)?
Answer:

A table is in Second Normal Form when:
- It is already in First Normal Form.
- Every non-key attribute depends on the whole candidate key, not just part of a composite candidate key.
This removes partial dependencies.

Example:

Suppose we have:

Enrollment(StudentID, CourseID, StudentName, CourseName, Grade)

The Primary Key is (StudentID, CourseID).

StudentName depends only on StudentID, and CourseName depends only on CourseID.

We should move these attributes to their respective tables.

Q25. What is Third Normal Form (3NF)?
Answer:

A table is in Third Normal Form when:
- It is already in Second Normal Form.
- It has no transitive dependencies of non-key attributes on candidate keys.
In simple words, non-key attributes should depend on the key, the whole key, and nothing but the key.

Example:

Employee(EmployeeID, DepartmentID, DepartmentName)

DepartmentName depends on DepartmentID, not directly on EmployeeID.

We should separate Department information into another table.

Q26. What is a Functional Dependency?
Answer:

A Functional Dependency describes a relationship where one attribute determines another attribute.

Example:

EmployeeID → EmployeeName

This means that EmployeeID determines the EmployeeName.

If two records have the same EmployeeID, they must have the same EmployeeName.

Q27. What is Denormalization?
Answer:

Denormalization is the process of intentionally adding redundant data to improve query performance.

It is often used in reporting systems and data warehouses to reduce the number of joins required.

Example:

Storing CustomerName alongside an Order record instead of retrieving it from the Customers table every time.

Interview note: Do not say denormalization is always better. It trades some storage and consistency complexity for potentially faster reads.

Asuraa+1

Section 4 — SQL Language and Commands

Q28. What is SQL?
Answer:

SQL stands for Structured Query Language.

It is a standard language used to communicate with relational databases to create, retrieve, manipulate, and manage data.
Q29. What is the difference between SQL and SQL Server?
Answer:

SQL is a query language used to interact with relational databases.

SQL Server is a Relational Database Management System developed by Microsoft that uses T-SQL, Microsoft's extension of SQL.

Q30. What are the main SQL Command Categories?
Answer:

SQL commands are commonly divided into four main categories:
Category	Meaning	Examples
DDL	Data Definition Language	CREATE, ALTER, DROP
DML	Data Manipulation Language	INSERT, UPDATE, DELETE
DCL	Data Control Language	GRANT, REVOKE
TCL	Transaction Control Language	COMMIT, ROLLBACK

Some learning materials classify SELECT separately as DQL (Data Query Language), while other classifications include it in DML.

Q31. What is the difference between DELETE, TRUNCATE, and DROP?
Answer:
- DELETE removes selected rows from a table and supports a WHERE condition.
- TRUNCATE removes all rows from a table but keeps its structure.
- DROP removes the entire table, including its structure.
Important SQL Server details:
- DELETE does not automatically reset an IDENTITY counter.
- TRUNCATE resets IDENTITY to its original seed.
- Both DELETE and TRUNCATE can be rolled back within an active SQL Server transaction.
- TRUNCATE cannot be used on a table referenced by a Foreign Key constraint.

Microsoft Learn+2

Q32. What is the difference between CHAR and VARCHAR?
Answer:

CHAR is a fixed-length data type, while VARCHAR is a variable-length data type.

Example:
CHAR(10)
VARCHAR(10)


CHAR uses a fixed declared length, while VARCHAR stores variable-length character data up to the specified limit.

Q33. What is IDENTITY in SQL Server?
Answer:

IDENTITY is a property that automatically generates sequential numeric values for a column.

It accepts two main values:
- Seed: The starting value.
- Increment: The value added for each new identity value.
Example:
EmployeeID INT IDENTITY(1,1)


The values normally start at 1 and increase by 1.

Important: IDENTITY does not guarantee uniqueness by itself. We need a Primary Key or UNIQUE constraint when uniqueness is required.

Q34. What is the difference between WHERE and HAVING?
Answer:

WHERE filters individual rows before grouping.

HAVING filters groups after the GROUP BY operation.

Example:
SELECT Department, AVG(Salary)
FROM Employees
WHERE Salary > 3000
GROUP BY Department
HAVING AVG(Salary) > 5000;


This query first filters employees, then groups them by department, and finally filters the groups based on their average salary.

Q35. What is NULL in SQL?
Answer:

NULL represents a missing or unknown value.

It is different from zero or an empty string.

We use IS NULL or IS NOT NULL to check for NULL values.

Example:
SELECT *
FROM Employees
WHERE Salary IS NULL;


We should not use Salary = NULL to test for NULL.

Q36. What is the difference between COUNT(*) and COUNT(ColumnName)?
Answer:

COUNT(*) counts all rows in the result set, including rows containing NULL values.

COUNT(ColumnName) counts only rows where that particular column is not NULL.

Example:

If a table has 10 rows and 3 NULL values in the Email column:
- COUNT(*) returns 10.
- COUNT(Email) returns 7.

systemdesign.academy+2

Section 5 — SQL Joins and Query Concepts
Study after WHERE and GROUP BY

Q37. What is a JOIN in SQL?
Answer:

A JOIN is used to combine data from two or more tables based on a related column between them.

Example:

We can JOIN Customers and Orders using CustomerID to retrieve customer information with their orders.

Q38. What are the different types of JOINs?
Answer:

There are several types of SQL JOINs:
JOIN	Description
INNER JOIN	Returns matching rows from both tables.
LEFT JOIN	Returns all rows from the left table and matching rows from the right table.
RIGHT JOIN	Returns all rows from the right table and matching rows from the left table.
FULL OUTER JOIN	Returns matching and non-matching rows from both tables.
CROSS JOIN	Returns every possible combination of rows.
SELF JOIN	Joins a table with itself.


Q39. What is the difference between INNER JOIN and LEFT JOIN?
Answer:

INNER JOIN returns only records that have matching values in both tables.

LEFT JOIN returns all records from the left table, even if there is no matching record in the right table.

When no match exists, the right-side columns contain NULL.

Q40. What is GROUP BY?
Answer:

GROUP BY is used to group rows that have the same values in specified columns.

It is commonly used with aggregate functions such as COUNT, SUM, AVG, MIN, and MAX.

Example:

We can calculate the total salary for each department using GROUP BY.

Q41. What are Aggregate Functions?
Answer:

Aggregate functions perform calculations on a set of rows and return a single result for each group.

Common aggregate functions include:
- COUNT: Counts records.
- SUM: Calculates the total.
- AVG: Calculates the average.
- MIN: Returns the minimum value.
- MAX: Returns the maximum value.
Q42. What is the difference between UNION and UNION ALL?
Answer:

UNION combines the results of two queries and removes duplicate rows.

UNION ALL combines the results and keeps duplicate rows.

UNION ALL is usually faster because it does not need to remove duplicates.
Q43. What is a Subquery?
Answer:

A subquery is a query written inside another SQL query.

It is used to provide a result that the main query depends on.

Example:

Finding employees whose salaries are greater than the average salary.

Section 6 — Transactions and ACID
Q44. What is a Transaction?
Answer:

A transaction is a logical unit of work that consists of one or more SQL statements.

It ensures that a group of operations can be committed together or rolled back when necessary.
Q45. What are ACID Properties?
Answer:

ACID represents four important properties of database transactions:
Property	Explanation
Atomicity	All operations succeed or none of them are applied.
Consistency	The transaction keeps the database within valid rules.
Isolation	Concurrent transactions are controlled to prevent incorrect interference.
Durability	Committed changes remain saved even after a system failure, subject to the database's durability guarantees.

Q46. What is the difference between COMMIT and ROLLBACK?
Answer:

COMMIT permanently saves the changes made during a transaction.

ROLLBACK cancels the uncommitted changes made during a transaction.

Example:

In a bank transfer, if money is deducted from one account but the second operation fails, ROLLBACK can cancel the deduction.
Q47. What is a SAVEPOINT?
Answer:

A SAVEPOINT marks a specific point inside a transaction.

It allows us to roll back part of a transaction without necessarily canceling the entire transaction.

Note: In SQL Server, the equivalent command is SAVE TRANSACTION.

Section 7 — Database Performance and Data Engineering Concepts
Later stage — don't study these deeply yet
Q48. What is an Index in a Database?
Answer:

An index is a data structure that helps the database retrieve records faster without scanning the entire table in many cases.

It improves read performance but requires additional storage and can slow down INSERT, UPDATE, and DELETE operations because the index must also be maintained.

Example:

An index on EmployeeID can help retrieve an employee faster when searching by EmployeeID.
Q49. What is the difference between Clustered and Non-Clustered Indexes?
Answer:

A clustered index defines how the table's data rows are organized by the index key.

A non-clustered index is a separate structure that stores indexed values and row references.

A table can have only one clustered index, but it can have multiple non-clustered indexes.

Q50. What is the difference between OLTP and OLAP?
Answer:

OLTP stands for Online Transaction Processing.

It is designed to handle daily business operations such as inserting orders, updating customer information, and processing payments.

OLAP stands for Online Analytical Processing.

It is designed to analyze large amounts of historical data and support business reporting and decision-making.

Example:
- OLTP: A customer places an order.
- OLAP: A company analyzes total sales for the last three yea
