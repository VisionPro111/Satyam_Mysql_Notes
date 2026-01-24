SHOW DATABASES;
--to show all the datbases available on your system.

USE <database name> ;
--to select a particular database to run queries on 

SHOW TABLES;
--to list down all the tables of a particular selected database

CREATE DATABASE <name>;
-- to create a new database

CREATE TABLE <name> (
    <column name 1> <datatype>,
    <column name 2> <datatype>
);

-- to create a new table


DESC <table name>;
-- show structure and description of the table

INSERT INTO <table name> (col1, col2, ...)
VALUES (value1, value2, ...);
-- to store values in table

SELECT <column name> FROM <table name>;
-- to select a specific column data from a table
-- use * in place of column name to get all the columns.

SELECT * FROM <table name> WHERE <conditions>;
-- comparisson of column data with your values.

SELECT * FROM second WHERE DoB > '2000-01-01' AND Gender = 'Female';

SELECT * FROM second ORDER BY DoB DESC;

SELECT * FROM second WHERE NOT Gender = 'Male';

SELECT * FROM second WHERE DoB > '2020-01-03' OR Gender = 'Female';


SELECT * FROM second WHERE Name LIKE 'a%';

SELECT * FROM second WHERE Name LIKE '%a%';

SELECT * FROM second
WHERE Gender = 'Female'
ORDER BY DoB DESC
LIMIT 2;