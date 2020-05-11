# Group by

The `Group by` statement groups rows that have the same values into summary rows.
Example: "Find the number of customers in each country".

The `Group by` statement is often used with aggregate functions (COUNT, MAX, MIN, SUM, AVG) to group the result-set by one or more columns.

#### SYNTAX

```sql
SELECT function(column_name)
FROM table_name
WHERE condition
GROUP BY column_name
ORDER BY column_name
```

##### Example using DB `Info`, table: `demo`:

```sql
USE info;
SELECT COUNT(id) AS PeopleFromCountry, id_country
FROM demo
GROUP BY id_country;
```

- res:

```sql
# PeopleFromCountry, id_country
'21', 'BR'
'38', 'BE'
'38', 'ZW'
'44', 'UK'
'45', 'NL'
'50', 'ZA'
'51', 'NG'
'52', 'CA'
'73', 'US'
'88', 'FR'
```

- Example: show the number of people that are above 50 for each country:

```sql
SELECT COUNT(id) AS PeopleFromCountry, id_country
FROM demo
WHERE age > 50
GROUP BY id_country DESC;
```
res:
```sql
# COUNT(id), id_country
'19', 'ZW'
'25', 'ZA'
'36', 'US'
'22', 'UK'
'26', 'NL'
'24', 'NG'
'44', 'FR'
'26', 'CA'
'15', 'BR'
'23', 'BE'
```

# Having

The HAVING clause was added to SQL because the WEHERE keyword could not be used with aggregate functions.

#### SYNTAX

```sql
SELECT function(column_name)
FROM table_name
WHERE condition
GROUP BY column_name
HAVING condition
ORDER BY column_name
```

- Example 1:

```sql
SELECT COUNT(id) AS PeopleFromCountry, id_country
FROM demo
GROUP BY id_country
HAVING COUNT(id) > 40;
```

- Example 2:

```sql
SELECT COUNT(id) AS PeopleFromCountry, id_country
FROM demo
GROUP BY id_country
HAVING COUNT(id) > 40
ORDER BY COUNT(id) DESC;
```
