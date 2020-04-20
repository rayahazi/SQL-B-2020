# Lesson queries

### 1. Check 
```sql

USE mall;

CREATE TABLE Person (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CHECK (Age>=18)
);


INSERT INTO Person(ID, LastName, FirstName, Age)
VALUES (1, 'Cohen', 'Israel',12);

SELECT * FROM Person;
```
##### Example:
A. Create table with many `CHECK` constraints
```sql

USE mall;

CREATE TABLE checkTbl(
	CHECK(c1 <> c2),
	c1 INT CHECK(c1 > 10),
    c2 INT,
    c3 INT CHECK(c3 < 100),
    CONSTRAINT c2_positive CHECK(c2 > 0),
    CONSTRAINT c3_nonzero  CHECK(c3 <> 0),
    CHECK (c1 > c3)
);
```
B. Insert data: 
```sql
-- Not valid: CHECK(c1 <> c2)
INSERT INTO checkTbl(c1, c2, c3)
VALUES (15, 15, 7)

-- Not valid: CHECK(c1 > 10), CHECK(c3 <> 0)
INSERT INTO checkTbl(c1, c2, c3)
VALUES (3, 4, 0)

-- Not valid: CHECK(c2 > 0), CHECK (c1 > c3)
INSERT INTO checkTbl(c1, c2, c3)
VALUES (20, 0 ,53)


-- Valid: 
INSERT INTO checkTbl(c1, c2, c3)
VALUES (30, 31, 25)
```

### 2. Default
ערך דיפולטיבי כאשר אנו לא מכניסים נתון לאותה עמודה

A. Create new table and insert columns to it. 
Add constraint `Default` for LastName = 'Levi'
```sql
USE mall;

CREATE TABLE Employee (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL DEFAULT 'Levi',
    FirstName varchar(255),
    Age int,
    CHECK (Age>=18)
);
```
B. Add rows to the table. 
We did not insert data to LastName, so the default value will be: `Levi`
```sql

INSERT INTO Employee(ID, FirstName, Age)
VALUES (2, 'John',20);

SELECT * FROM Employee;

```
C. Result:
```sql
2	Levi	John	20
```

#### Example:
A. Create table `defaultTBL` with 3 diffrent DEFAULT values
```sql

USE mall;

CREATE TABLE defaultTBL(
    d1 INT DEFAULT -1,
    d2 VARCHAR(10) DEFAULT '',
    d3 BOOLEAN DEFAULT TRUE
);
```
B. Insert data only to `d2` column
```sql

INSERT INTO defaultTBL(d2)
VALUES ('a');

SELECT * FROM defaultTBL;
```
C. Result:
```
# d1, d2,  d3
'-1', 'a', '1'
```
#### Real life example: 
```sql

CREATE TABLE Students(

    FullName NVARCHAR(20),
    Country  NVARCHAR(20) DEFAULT 'ISRAEL',
    IsMale   BOOLEAN DEFAULT TRUE
    
);
```

### 3. Auto_increment
#### Example:
A. Create table `animals` and define ID as primary-key and auto-increment
```sql

USE mall;

CREATE TABLE animals(
    ID INT NOT NULL AUTO_INCREMENT,
    FullName NVARCHAR(20) NOT NULL,
    PRIMARY KEY(ID)
);

```
B. Insert data into the table. (Without the ID column).
```sql

INSERT INTO animals(FullName)
VALUES ('dog'),('cat'),('dolphin');
```
C. Get the table data:
```sql

SELECT * FROM animals;

```
D. We can see that both columns are full with data. 
(Even though we did not insert data to the `ID` column)
```
# ID, FullName
'1', 'dog'
'2', 'cat'
'3', 'dolphin'
```

#### Another example:
```sql
CREATE TABLE Categories(
    ID INT AUTO_INCREMENT CHECK(ID <> 10),
    category_name VARCHAR(20) DEFAULT NULL, 
    notes VARCHAR(20) DEFAULT NULL, 
    PRIMARY KEY(ID)
);
```