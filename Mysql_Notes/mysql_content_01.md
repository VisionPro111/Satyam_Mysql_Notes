# MySQL – Content 2026  
**Trainer:** SATYAM  

---

## 1. Create Actors Table

```sql
CREATE TABLE Actors (
    ID INT PRIMARY KEY AUTO_INCREMENT,
    FirstName VARCHAR(25),
    LastName VARCHAR(25),
    DoB DATE,
    Gender ENUM('Male','Female','Other'),
    MaritalStatus ENUM('Single','Married'),
    NetWorthInMillion INT
);
```

---

## 2. Insert Data into Actors Table

```sql
INSERT INTO Actors
(ID, FirstName, LastName, DoB, Gender, MaritalStatus, NetWorthInMillion)
VALUES
(1, 'Brad', 'Pitt', '1963-12-18', 'Male', 'Single', NULL),
(3, 'George', 'Clooney', '1962-05-06', 'Male', 'Married', NULL),
(4, 'Johnny', 'Depp', '1963-06-09', 'Male', 'Single', NULL),
(6, 'RJ', NULL, '1950-12-12', 'Male', 'Married', 1000);
```

---

## 3. Update Queries

### Update first name of actor with ID = 6

```sql
UPDATE Actors
SET FirstName = 'Rajnikanth'
WHERE ID = 6;
```

Verify:
```sql
SELECT * FROM Actors WHERE ID = 6;
```

---

### Update Multiple Columns

```sql
UPDATE table_name
SET column1 = value1,
    column2 = value2,
    column3 = value3
WHERE condition;
```

---

### Update first name and marital status of actor with ID = 4

```sql
UPDATE Actors
SET FirstName = 'John',
    MaritalStatus = 'Married'
WHERE ID = 4;
```

---

## 4. Alter Table Queries

### Rename NetWorthInMillion to NetWorth

```sql
ALTER TABLE Actors
CHANGE NetWorthInMillion NetWorth DECIMAL(10,2);
```

---

### Add Region column

```sql
ALTER TABLE Actors
ADD Region VARCHAR(50) DEFAULT 'Bollywood';
```

---

### Update all Region values

```sql
UPDATE Actors
SET Region = 'Hollywood';
```

---

### Update Salary between IDs 3 and 6

```sql
UPDATE Actors
SET Salary = 10000
WHERE ID BETWEEN 3 AND 6;
```

---

### Update MaritalStatus for IDs 1,4,6

```sql
UPDATE Actors
SET MaritalStatus = 'Married'
WHERE ID IN (1,4,6);
```

---

### Add MiddleName column

```sql
ALTER TABLE Actors
ADD MiddleName VARCHAR(50) NULL;
```

---

### Drop MiddleName column

```sql
ALTER TABLE Actors
DROP COLUMN MiddleName;
```

---

## 5. SQL Terms

- DISTINCT – removes duplicate rows  
- COUNT(*) – counts rows  
- COUNT(DISTINCT col) – counts unique values  
- CONCAT – joins strings  
- WHERE – filter data  
- ORDER BY – sort data  
- LIMIT / TOP – select first N rows  
- LIKE – pattern search  

---

## 6. SELECT Queries

```sql
SELECT FirstName, LastName FROM Actors;
```

```sql
SELECT CONCAT(FirstName,' ',LastName) AS FullName FROM Actors;
```

```sql
SELECT DISTINCT Region FROM Actors;
```

```sql
SELECT COUNT(*) AS MaleActors FROM Actors WHERE Gender='Male';
```

```sql
SELECT FirstName, LastName FROM Actors
WHERE Gender='Male' AND MaritalStatus='Married';
```

```sql
SELECT FirstName, LastName, DoB FROM Actors ORDER BY DoB ASC;
```

```sql
SELECT * FROM Actors LIMIT 3;
```

---

## 7. LIKE Operator Queries

```sql
SELECT * FROM Actors WHERE FirstName LIKE 'J%';
```

```sql
SELECT * FROM Actors WHERE LastName LIKE '%y';
```

```sql
SELECT * FROM Actors WHERE FirstName LIKE '%oh%';
```