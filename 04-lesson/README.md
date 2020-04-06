# Lesson 04

#### Add a column name: `age` to the table: `salesman`: 

```sql
USE mall;

SELECT * FROM salesman;

ALTER TABLE salesman
ADD age INT;
```

```sql
# salesman_id, name, city, commission, age
'5001', 'James Hoog', 'New York', '0.15', NULL
'5002', 'Nail Knite', 'Paris', '0.13', NULL
'5005', 'Pit Alex', 'London', '0.11', NULL
'5006', 'Mc Lyon', 'Paris', '0.14', NULL
'5007', 'Paul Adam', 'Rome', '0.13', NULL
'5003', 'Lauson Hen', 'San Jose', '0.12', NULL
```

#### Delete the column `age` from table: `salesman`: 

```sql
USE mall;

SELECT * FROM salesman;

ALTER TABLE salesman
DROP age;
```

```sql
# salesman_id, name, city, commission
'5001', 'James Hoog', 'New York', '0.15'
'5002', 'Nail Knite', 'Paris', '0.13'
'5005', 'Pit Alex', 'London', '0.11'
'5006', 'Mc Lyon', 'Paris', '0.14'
'5007', 'Paul Adam', 'Rome', '0.13'
'5003', 'Lauson Hen', 'San Jose', '0.12'
```

#### Change the type of the column `name` from `nvarchar(20)` to `varchar(20)`:

```sql
USE mall;

SELECT * FROM salesman;

ALTER TABLE salesman
MODIFY COLUMN name varchar(20);
```

```sql
# salesman_id, name, city, commission
'5001', 'James Hoog', 'New York', '0.15'
'5002', 'Nail Knite', 'Paris', '0.13'
'5005', 'Pit Alex', 'London', '0.11'
'5006', 'Mc Lyon', 'Paris', '0.14'
'5007', 'Paul Adam', 'Rome', '0.13'
'5003', 'Lauson Hen', 'San Jose', '0.12'
```

#### Another example: lose data when modifing a column:

```sql
USE mall;

SELECT * FROM salesman;

ALTER TABLE salesman
MODIFY COLUMN name varchar(5);
```

```sql
# salesman_id, name, city, commission
'5001', 'James', 'New York', '0.15'
'5002', 'Nail ', 'Paris', '0.13'
'5005', 'Pit A', 'London', '0.11'
'5006', 'Mc Ly', 'Paris', '0.14'
'5007', 'Paul ', 'Rome', '0.13'
'5003', 'Lauso', 'San Jose', '0.12'
```
* This is an warning that comes after we change the column. (we can lose data). 
```
09:26:48	ALTER TABLE salesman MODIFY COLUMN name varchar(5)	6 row(s) affected, 6 warning(s): 1265 Data truncated for column 'name' at row 1 1265 Data truncated for column 'name' at row 2 1265 Data truncated for column 'name' at row 3 1265 Data truncated for column 'name' at row 4 1265 Data truncated for column 'name' at row 5 1265 Data truncated for column 'name' at row 6 Records: 6  Duplicates: 0  Warnings: 6	0.125 sec
```


#### Delete a row from table `salesman`:

```sql
USE mall;

SELECT * FROM salesman;

DELETE FROM salesman
WHERE salesman_id = 5001;

```

* Note: if an error occures: 
```
Go to Edit --> Preferences
Click "SQL Editor" tab and uncheck "Safe Updates" check box
Query --> Reconnect to Server // logout and then login
Now execute your SQL query

```
## Constraints:

```sql
USE mall;

CREATE TABLE Persons (
    ID        int NOT NULL,
    LastName  varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int
);

SELECT * FROM Persons;

ALTER TABLE Persons
ADD UNIQUE (ID);


INSERT INTO Persons(ID, LastName, FirstName, Age)
VALUES (1, 'Levi','Shay', 60);

```


## See database diagram:

Database -> Reverse Engeneering -> select the database to show diargam. 


