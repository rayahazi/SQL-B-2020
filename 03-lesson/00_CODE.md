# The code we used in class

##### Insert one row to table: 
```sql
USE mall;

INSERT INTO foodstore (ID, FullName, Category, Amount, Price, Expiration_date)
VALUES (1, 'Salmon','Fish', 50, 20.5, '2020-05-01')
```

##### Insert many rows to table: 
```sql
-- This is an one line comment
USE mall;

INSERT INTO foodstore (ID, FullName, Category, Amount, Price, Expiration_date)
VALUES (2, 'Choclate','Sweets', 100, 8.5, '2020-08-01'),
	   (3, 'Milk','Cheezy', 125, 5.8, '2020-03-30')
```

##### Show the table data: 
```sql
USE mall;

SELECT * FROM foodstore;
```

##### Select specific columns: 
בוחר עמודות ספציפיות
```sql
SELECT FullName, Price, Expiration_date FROM foodstore;
```


##### Select only the categories that are in the store:
##### Select distinct: Will show us only the first instance of an item. 
חלק זה יראה לנו את המופע הראשון של כל פריט. 
אם פריט חוזר על עצמו כמה פעמים - לא יוצג. 
```sql
SELECT Category FROM foodstore;
```
##### Category
'Fish'
'Sweets'
'Cheezy'
'Fish'

```sql
SELECT DISTINCT Category FROM foodstore;
```
#### Category
'Cheezy'
'Fish'
'Sweets'

##### Show how many rows are:
```sql
SELECT COUNT(ID) FROM foodstore;
```


# Where

### Show only rows that their amount = 50
נציג רק את השורות שבהן כמות = 50
```sql
SELECT * FROM foodstore
WHERE Amount = 50;

```
Result:
```sql
# ID, FullName, Category, Amount, Price, Expiration_date
'1', 'Salmon', 'Fish', '50', '20.5', '2020-05-01'
'4', 'Nilus', 'Fish', '50', '20.5', '2020-05-01'
```

### Show only rows that their amount > 50

```sql
SELECT * FROM foodstore
WHERE Amount > 50;
```
Result:
```sql
# ID, FullName, Category, Amount, Price, Expiration_date
'2', 'Choclate', 'Sweets', '100', '8.5', '2020-08-01'
'3', 'Milk', 'Cheezy', '125', '5.8', '2020-03-30'
```
### Show only rows that their amount is diffrent than 100
```sql
SELECT * FROM foodstore
WHERE Amount <> 100;
```
Result:
```sql
# ID, FullName, Category, Amount, Price, Expiration_date
'1', 'Salmon', 'Fish', '50', '20.5', '2020-05-01'
'3', 'Milk', 'Cheezy', '125', '5.8', '2020-03-30'
'4', 'Nilus', 'Fish', '50', '20.5', '2020-05-01'
```
### Show only rows that their `FullName` starts with 'M'
```sql
SELECT * FROM foodstore
WHERE FullName LIKE 'M%';

```
Result:
```sql
# ID, FullName, Category, Amount, Price, Expiration_date
'3', 'Milk', 'Cheezy', '125', '5.8', '2020-03-30'
```
### Show only rows that their `FullName` is the same as the values in the `IN` clause

```sql
SELECT * FROM foodstore
WHERE FullName IN('Salmon','Milk');
```
Result:
```sql
# ID, FullName, Category, Amount, Price, Expiration_date
'1', 'Salmon', 'Fish', '50', '20.5', '2020-05-01'
'3', 'Milk', 'Cheezy', '125', '5.8', '2020-03-30'
```

# AND, OR, NOT:
```
Bit = 0 / 1

AND:
1 AND 1 = 1
1 AND 0 = 0
0 AND 1 = 0
0 AND 0 = 0

OR:
1 OR 1 = 1
1 OR 0 = 1
0 OR 1 = 1
0 OR 0 = 0

NOT:
1 NOT = 0
0 NOT = 1

```




## Show two options: 
```sql
SELECT * FROM foodstore
WHERE (FullName = 'Nilus') OR (ID = 3);
```
Result:
```sql
# ID, FullName, Category, Amount, Price, Expiration_date
'3', 'Milk', 'Cheezy', '125', '5.8', '2020-03-30'
'4', 'Nilus', 'Fish', '50', '20.5', '2020-05-01'
```
## Use and + or: 

```sql
SELECT * FROM foodstore
WHERE (Category = 'Fish' AND ID = 1) OR (Amount = 125);
```
Result:
```sql
# ID, FullName, Category, Amount, Price, Expiration_date
'1', 'Salmon', 'Fish', '50', '20.5', '2020-05-01'
'3', 'Milk', 'Cheezy', '125', '5.8', '2020-03-30'
```

# Order by:
Order by Price: (Default: Ascending)

```sql

SELECT * FROM foodstore
ORDER BY Price;

```
OR:
```sql
SELECT * FROM foodstore
ORDER BY Price ASC;
```

Result:
```sql
# ID, FullName, Category, Amount, Price, Expiration_date
'3', 'Milk', 'Cheezy', '125', '5.8', '2020-03-30'
'2', 'Choclate', 'Sweets', '100', '8.5', '2020-08-01'
'1', 'Salmon', 'Fish', '50', '20.5', '2020-05-01'
'4', 'Nilus', 'Fish', '50', '20.5', '2020-05-01'
```


### Descending
```sql

SELECT * FROM foodstore
ORDER BY Amount DESC;
```

Result:
```sql
# ID, FullName, Category, Amount, Price, Expiration_date
'3', 'Milk', 'Cheezy', '125', '5.8', '2020-03-30'
'2', 'Choclate', 'Sweets', '100', '8.5', '2020-08-01'
'1', 'Salmon', 'Fish', '50', '20.5', '2020-05-01'
'4', 'Nilus', 'Fish', '50', '20.5', '2020-05-01'
```



