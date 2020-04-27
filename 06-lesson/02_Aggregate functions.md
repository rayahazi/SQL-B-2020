# Aggregate functions

#### table of contents:

1. MIN()
2. MAX()
3. AVG()
4. COUNT()
5. SUM()
6. RAND()
7. LIMIT

## MIN 

Returns the minimum value of `expr`. 

MIN() can take a string argument. 

If there are no matching rows - MIN() returns NULL. 

```sql
SELECT MIN(column_name) 
FROM table_name
WHERE condition
```
Example: (from db `info`, table `demo`)
```sql
SELECT MIN(age) 
FROM demo;      -- 15
```
```sql
SELECT MIN(age) AS YoungestEmployee
FROM demo;      -- 15

-- RESULT:

# YoungestEmployee
'15'
```
Example: using MIN() with string-type columns
```sql
SELECT MIN(name) AS MinimumName 
FROM demo;      -- Abbott
```
Example: use `WHERE` clause to strict the output. 
```sql
SELECT MIN(age) AS MinimumName 
FROM demo
WHERE age > 30; -- 31
```
## MAX 
Returns the maximum value of `expr`. 

MAX() can take a string argument. 

If there are no matching rows - MAX() returns NULL. 

```sql
SELECT MAX(column_name) 
FROM table_name
WHERE condition
```
Example: select the tallest person in the table
```sql
SELECT MAX(height) AS TallestEmp
FROM demo; -- 1.99
```
Example: select the name that starts with the greatest value (according to ASCII table). 
```sql
SELECT MAX(firstname)
FROM demo; -- Zorita
```

## AVG (Average) - ממוצע
Returns the average value of `expr`. The `DISTINCT` option can be used to return the average of values of `expr`.

If there are no matching rows - AVG() returns NULL.

Example: Get the average age of people in the table: 
```sql
SELECT AVG(age)
FROM demo;      -- 52.34
```
* Example: Use `DISTINCT` with `AVG()` function.

**Simple AVG():**

1, 1, 3, 5, 8, 1

AVG = ( 1 + 1 + 3 + 5 + 8 + 1 ) / 6  = 3.16

**Distinct AVG():**

1, 3, 5, 8

AVG = ( 1 + 3 + 5 + 8  ) / 4  = 4.25

```sql
SELECT AVG(DISTINCT age)
FROM demo;	  -- 52.5
```


Example: AVG() isn't working on string columns. 
```sql
SELECT AVG(firstname)
FROM demo;      -- 0
```



## COUNT() 
Returns a count of the number of non-NULL values of `expr` in the rows retrieved by SELECT statement. 

If there are no matching rows - COUNT() returns 0.


* Example: Select the amount of rows in table. 
Here we get the full amount of rows. The reason: we used the `id` column. and it must be primary key. (can't be NULL). 
```sql
SELECT COUNT(id) 
FROM demo; -- 500
```

* Example: COUNT(*) - will retrieve the amount of rows in the table, whether they include NULL of not. 
```sql
SELECT COUNT(*) FROM demo; -- 500
```

* Example: COUNT(DISTINCT column_name) - we get one apparence of each age. 
```sql
SELECT COUNT(DISTINCT age) FROM demo; -- 76
```

## SUM() - סכום
Returns the sum of `expr`. 
If there are no matching rows - SUM() returns NULL.

```sql
SELECT SUM(age) FROM demo;    -- 26170
SELECT SUM(height) FROM demo; -- 747.45
```


## RAND() - random (אקראי)
Returns a random number between 0 to 1 

```sql
SELECT RAND(); -- '0.0802365355940876'
SELECT RAND(); -- '0.5659724227767181'
```

**Seed** - Optional. If seed is specified, it returns a repeatable sequence of random numbers. If no seed specified, it returns a completely random number. 
```sql
SELECT RAND(6); -- '0.6563190842571847'
```
* Return a random number >=5 and < 10
```sql
SELECT RAND()*(10-5)+5;
-- '5.211560768272319'
-- '8.349925846187329'

```
* Return integer random number >=5 and < 10
```sql
SELECT RAND(); -- '0.10499160280916058'
SELECT RAND()*(10-5)+5;
SELECT FLOOR(RAND()*(10-5)+5); -- 9 , 7 etc...
```

## LIMIT
Returns the number of rows we define in LIMIT area, that fit the clauses above.  

* Example: select 5 rows, that ordered by descending names. 
```sql
SELECT * FROM demo
ORDER BY name DESC
LIMIT 5;
```
Result:
```sql
# id, name, firstname, age, height, id_continent, id_country, email, freelance, lastvisit, website
'361', 'Zamora', 'Kyla', '16', '1.76', 'eu', 'NL', 'rutrum@Uttincidunt.ca', '0', '2012-02-05', 'www.zmkjzeqlaqe.ajw'
'411', 'Woodward', 'Leonard', '20', '1.34', 'af', 'NG', 'vestibulum@tristiqueneque.com', '0', '2012-03-29', 'www.bhwhnfykiyr.kgd'
'91', 'Wong', 'Marcia', '83', '1.59', 'na', 'US', 'leo@acmattisvelit.org', '0', '2012-01-29', 'www.vsgxsvdmjch.hqh'
'460', 'Wolfe', 'Althea', '28', '1.61', 'af', 'NG', 'imperdiet.ullamcorper@Duisami.edu', '0', '2012-04-24', 'www.edwpjjwwvwi.aln'
'358', 'Wolf', 'Fuller', '67', '1.69', 'na', 'CA', 'blandit@placerat.ca', '0', '2012-05-03', 'www.vlmjtppnjor.bep'
```
* Example: select 5 rows, with only 3 important columns, that ordered by descending names.
```sql
SELECT id, name, age FROM demo
ORDER BY name DESC
LIMIT 5;
```
Result:
```sql
# id, name, age
'361', 'Zamora', '16'
'411', 'Woodward', '20'
'91', 'Wong', '83'
'460', 'Wolfe', '28'
'358', 'Wolf', '67'

```