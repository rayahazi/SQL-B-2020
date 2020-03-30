# Where
The WHERE clause is used to filter records.

The WHERE clause is used to extract only those records that fulfill a specified condition.
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
### Operators in The WHERE Clause
```
=  	Equal	
>	Greater than	
<	Less than	
>=	Greater than or equal	
<=	Less than or equal	
<>	Not equal. Note: In some versions of SQL this operator may be written as !=	
BETWEEN	  Between a certain range	
LIKE	Search for a pattern	
IN	To specify multiple possible values for a column
```
### Example:
* Between:
```sql
SELECT * FROM Products
WHERE Price BETWEEN 50 AND 60;
```

* Like:
```sql
SELECT * FROM Customers
WHERE City LIKE 's%';
```
* In:
```sql
SELECT * FROM Customers
WHERE City IN ('London','Paris');
```
