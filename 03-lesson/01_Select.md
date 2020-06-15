# Lesson 03

### Comments (-- or /**/)
```sql
-- This is inline comment

/*
    This is multiple line comment
    As you see
*/

```
### Insert data into table
```sql
use `database`
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```
Insert Data Only in Specified Columns: It is also possible to only insert data in specific columns.

---

## Select, select distinct
* SELECT: 
    The SELECT statement is used to select data from a database.
    The data returned is stored in a result table, called the result-set.
```sql
SELECT column1, column2, ...
FROM table_name;

 -- * = all
SELECT * FROM table_name;

```
* select distinct:
    The SELECT DISTINCT statement is used to return only distinct (different) values.
    Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values.
```sql
SELECT DISTINCT FROM `table_name`

-- COUNT is a function
SELECT COUNT(DISTINCT Country) FROM Customers;

```





