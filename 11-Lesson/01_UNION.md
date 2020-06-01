# Code

1. select cities from both `customer` and `salesman`

```sql
use class;

SELECT city FROM customer
UNION
SELECT city FROM salesman;
```

- res: returns results without repetition. (select distinct)

```sql
# city
'New York'
'California'
'London'
'Paris'
'Berlin'
'Moscow'
'Rome'
'San Jose'
```

### UNION ALL

```sql

SELECT city FROM customer
UNION ALL
SELECT city FROM salesman
ORDER BY city DESC;

```

- res: returns all the options, including repetitive content.

```sql
# city
'San Jose'
'San Jose'
'Rome'
'Rome'
'Paris'
'Paris'
'Paris'
'Paris'
'Paris'
'Paris'
'New York'
'New York'
'New York'
'New York'
'New York'
'New York'
'Moscow'
'Moscow'
'London'
'London'
'London'
'London'
'London'
'London'
'California'
'California'
'Berlin'
'Berlin'
```
* write a query to display both id and name of customer and salesman

```sql
SELECT customer_id as ID, cust_name as UserName FROM customer
UNION
SELECT salesman_id as ID, name as UserName FROM salesman
ORDER BY ID
```
```sql
# ID, UserName
'3001', 'Brad Guzan'
'3002', 'Nick Rimando'
'3003', 'Jozy Altidor'
'3004', 'Fabian Johnson'
'3005', 'Graham Zusi'
'3007', 'Brad Davis'
'3008', 'Julian Green'
'3009', 'Geoff Cameron'
'5001', 'James Hoog'
'5002', 'Nail Knite'
'5003', 'Lauson Hen'
'5005', 'Pit Alex'
'5006', 'Mc Lyon'
'5007', 'Paul Adam'
```