# Create the table:
```sql
USE mall;

CREATE TABLE Salesman(
	salesman_id INT,
    name NVARCHAR(20), 
    city NVARCHAR(20),
    commission FLOAT
)
```

# Insert data into table:
```sql

INSERT INTO Salesman(salesman_id,name,city,commission) 
VALUES( 5001,'James Hoog','New York',0.15),
	  (  5002,'Nail Knite','Paris', 0.13),
	  ( 5005,'Pit Alex','London', 0.11),
	  (5006,'Mc Lyon','Paris',0.14),
	  (5007,'Paul Adam','Rome',0.13),
      (5003,'Lauson Hen','San Jose',0.12)

```


2. 
```sql
SELECT * FROM Salesman;
```

3. 
```sql
SELECT name,commission FROM Salesman;
```
4. 
```sql
SELECT name,city FROM Salesman
WHERE city='paris';
```
5. 
```sql
SELECT * FROM Salesman
WHERE city='Paris' OR city='Rome';
```
6. 
```sql
SELECT * FROM Salesman
WHERE city IN('Paris', 'Rome');
```
7. 
```sql
SELECT * FROM Salesman
WHERE NOT city IN('Paris', 'Rome');

```
8. 
```sql
SELECT * FROM Salesman
WHERE commission BETWEEN 0.12 AND 0.14;
```
9. 
```sql
SELECT * FROM Salesman
WHERE name BETWEEN 'A' AND 'L';

```



