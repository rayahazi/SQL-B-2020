# Joins
A JOIN clause is used to combine rows from two or more tables, based on a related column between them.

## Different Types of SQL JOINs
Here are the different types of the JOINs in SQL:
<img src="https://www.w3schools.com/sql/img_innerjoin.gif"/>
* **(INNER) JOIN**: Returns records that have matching values in both tables
```sql
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```

<img src="https://www.w3schools.com/sql/img_leftjoin.gif"/>

* **LEFT (OUTER) JOIN**: Returns all records from the left table, and the matched records from the right table
```sql
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

<img src="https://www.w3schools.com/sql/img_rightjoin.gif"/>

* **RIGHT (OUTER) JOIN**: Returns all records from the right table, and the matched records from the left table
```sql
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```

