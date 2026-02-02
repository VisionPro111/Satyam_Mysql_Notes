--How to Access SQL Using XAMPP
For Windows Users
Step 1: Install XAMPP

Download and install XAMPP for Windows
During installation, allow required permissions if prompted

Step 2: Start MySQL Server

Open XAMPP Control Panel
Click Start next to MySQL
Ensure the status shows Running

Open the Command Prompt.
cd C:\xampp\mysql\bin			// access the bin folder	
mysql -u root				// for default username root, access that username
mysql -u root -p			// -p for password if specified any, otherwise enter.

--For macOS Users
Step 1: Install and Run XAMPP

Install XAMPP and allow required permissions from System Settings → Privacy & Security
Open XAMPP Control Panel
Go to Manage Servers

Start the following services:
Apache Web Server
MySQL Database

Step 2: Access MySQL Using Terminal

Open Terminal
Execute the following command

sudo /Applications/XAMPP/xamppfiles/bin/mysql.server start

/Applications/XAMPP/xamppfiles/bin/mysql -u root 


/////////////

SQL Commands | DDL, DQL, DML, DCL & TCL

SQL commands are used to perform operations on a database such as creating tables, inserting data, querying records, managing permissions, and handling transactions.

SQL commands are broadly classified into five categories:

1. DDL – Data Definition Language

DDL commands are used to define, modify, or remove database structures like tables, schemas, and indexes.
These commands affect the database schema, not the data itself.

Common DDL Commands:
CREATE
DROP
ALTER
TRUNCATE
COMMENT
RENAME

Example:-
CREATE TABLE students (
    id INT,
    name VARCHAR(50),
    age INT
);

2. DQL – Data Query Language

DQL is used to retrieve data from the database.
The primary command is SELECT, which returns data in the form of a result set.

Example:
SELECT name, age
FROM students
WHERE age > 18
ORDER BY age;

Common SELECT Clauses:

FROM
WHERE
GROUP BY
HAVING
DISTINCT
ORDER BY
LIMIT

Note:
DQL has only one command: SELECT.
All other keywords are clauses of SELECT, not independent commands.


3. DML – Data Manipulation Language

DML commands are used to manipulate data inside tables.
They allow inserting, updating, and deleting records.

Common DML Commands:

INSERT
UPDATE
DELETE
 
example:-
INSERT INTO students VALUES (1, 'Alice', 20);

UPDATE students
SET age = 21
WHERE id = 1;

DELETE FROM students
WHERE id = 1;

4. DCL – Data Control Language

DCL commands manage user permissions and access control in a database.

Common DCL Commands:

GRANT
REVOKE

Example:-

GRANT SELECT, INSERT ON students TO user1;
REVOKE INSERT ON students FROM user1;

5. TCL – Transaction Control Language

TCL commands are used to manage transactions.
A transaction is a group of SQL operations treated as a single unit of work.

If all operations succeed → COMMIT
If any operation fails → ROLLBACK

Common TCL Commands:

BEGIN TRANSACTION
COMMIT
ROLLBACK
SAVEPOINT

Example:
BEGIN TRANSACTION;

INSERT INTO students VALUES (2, 'Bob', 22);
SAVEPOINT sp1;

DELETE FROM students WHERE id = 2;

ROLLBACK TO sp1;
COMMIT;

Interview Point:

TCL ensures ACID properties (Atomicity, Consistency, Isolation, Durability).



-------------------------
DATA TYPES:

CHAR(n)
1. Fixed-length character data
Size: 0 - 255
If data is shorter, remaining space is padded with spaces
Example: CHAR (10) → "city" uses 4 chars, 6 spaces added
2. VARCHAR(n)
Variable-length character data
Size: 0 - 65535
Stores only actual data length
Example: VARCHAR (30) → "city" uses only 4 characters
3. INT
Used for integer values
Size: 4 bytes
Range: -2147483648 to 2147483647
For larger values → use BIGINT (8 bytes)
4. FLOAT
Used for decimal numbers
Size: 4 bytes
Example: 12.45,98.6
5. DATE
Used to store date values
Format: YYYY-MM-DD
Range: 1000-01-01 to 9999-12-31

CONSTRAINTS
1. NOT NULL
• Prevents a column from having NULL values
2. UNIQUE
• Ensures all values in a column are different
3. DEFAULT
• Assigns a default value if no value is provided
4. PRIMARY KEY
Uniquely identifies each record in a table
Cannot be NULL and must be UNIQUE


# MySQL – Content 2026 
**Trainer:** SATYAM  

---

## 1. Database Commands

### Select a Database
```sql
USE database_name;
```
*Used to select a particular database to run queries on.*

---

### Show All Tables
```sql
SHOW TABLES;
```
*Displays all tables present in the selected database.*

---

### Create a New Database
```sql
CREATE DATABASE database_name;
```
*Creates a new database.*

---

## 2. Table Commands

### Create a Table
```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype
);
```
*Creates a new table with specified columns and data types.*

---

### Describe a Table
```sql
DESC table_name;
```
*Shows structure, data types, and constraints of a table.*

---

## 3. Insert Data

```sql
INSERT INTO table_name (col1, col2, ...)
VALUES (value1, value2, ...);
```
*Used to insert records into a table.*

---

## 4. Select Queries

### Select Specific Columns
```sql
SELECT column_name FROM table_name;
```
*Fetches specific column data.*

---

### Select All Columns
```sql
SELECT * FROM table_name;
```
*Fetches all columns from a table.*

---

### Select with WHERE Condition
```sql
SELECT * FROM table_name WHERE condition;
```
*Filters records based on conditions.*

---

## 5. Conditional Queries Examples

### Using AND Operator
```sql
SELECT * FROM second
WHERE DoB > '2000-01-01'
AND Gender = 'Female';
```

---

### Sorting Records
```sql
SELECT * FROM second
ORDER BY DoB DESC;
```

---

### Using NOT Operator
```sql
SELECT * FROM second
WHERE NOT Gender = 'Male';
```

---

### Using OR Operator
```sql
SELECT * FROM second
WHERE DoB > '2020-01-03'
OR Gender = 'Female';
```

---

## 6. LIKE Operator (Pattern Matching)

### Names Starting with 'a'
```sql
SELECT * FROM second
WHERE Name LIKE 'a%';
```
*Finds names that start with letter 'a'.*

---

### Names Containing 'a'
```sql
SELECT * FROM second
WHERE Name LIKE '%a%';
```
*Finds names that contain letter 'a' anywhere.*

---

## 7. ORDER BY with LIMIT

```sql
SELECT * FROM second
WHERE Gender = 'Female'
ORDER BY DoB DESC
LIMIT 2;
```
*Fetches the latest two female records based on Date of Birth.*
