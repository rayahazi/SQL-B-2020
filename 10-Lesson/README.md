# Subqueries - תת שאילתות

##### A subquery is SQL query nested(מקוננת) inside a larger query.

A subquery can come with:

1. SELECT
2. FROM
3. WHERE

- A subquery can be nested inside a SELECT, INSERT, UPDATE or DELETE statements. Or inside another subquery.

- We can use comparison operators: `>= <= = IN ANY ALL`
- A subquery also called `inner query`.

* A subquery is executed **first!** before the larger query. so that the results can be passed to the parent query.

## Examples:

#### 1. Write a query to display all orders from the table, that connected to salesman - `Paul Adam`

```sql
SELECT * FROM orders
WHERE salesman_id = (
		SELECT salesman_id
        FROM salesman
        WHERE name = 'Paul Adam');
/*
# ord_no, purch_amt, ord_date, customer_id, salesman_id
'70011', '75.29', '2012-08-17', '3003', '5007'
*/

-- same as writing the 2 queries:
SELECT * FROM salesman
WHERE name = 'Paul Adam'; -- 5007
SELECT * FROM orders
WHERE salesman_id = 5007;

```

#### 2. Write a query to display all orders from the table, that belong to salesman from `London`

```sql
use class;

SELECT salesman_id, name FROM salesman
WHERE city = 'London'; -- 5005
SELECT * FROM orders
WHERE salesman_id = 5005;

SELECT * FROM orders
WHERE salesman_id = (
		SELECT salesman_id
        FROM salesman
        WHERE city = 'London');
/*
# ord_no, purch_amt, ord_date, customer_id, salesman_id
'70009', '270.65', '2012-09-10', '3001', '5005'
*/

```

#### 3. Write a query to display all orders from the table, that belong to customer_id = 3007

```sql
use class;

SELECT cust_name, customer_id FROM customer
WHERE cust_name = 'Brad Davis'; -- 3007
SELECT * FROM orders
WHERE customer_id = 3007;

SELECT * FROM orders
WHERE customer_id = (
		SELECT customer_id
        FROM customer
        WHERE cust_name = 'Brad Davis');
/*
# ord_no, purch_amt, ord_date, customer_id, salesman_id
'70005', '2400.60', '2012-07-27', '3007', '5001'
*/
```

#### 4. Write a query to display all orders from the table, where `purch_amt` is greater than the average purch_amt from date: `2012-04-25`

```sql

SELECT AVG(purch_amt) FROM orders
WHERE ord_date = '2012-04-25'; -- '3045.600000'
SELECT * FROM orders
WHERE purch_amt > 3045.600000;

SELECT * FROM orders
WHERE purch_amt > (
		SELECT AVG(purch_amt)
        FROM orders
		WHERE ord_date = '2012-04-25');
/*
# ord_no, purch_amt, ord_date, customer_id, salesman_id
'70008', '5760.00', '2012-09-10', '3002', '5001'
*/
```

#### 5. Write a query to display all orders from the table, where salesman is from 'New York'. (use IN).

```sql
SELECT * FROM salesman
WHERE city = 'New York'; -- '5001, James Hoog'
SELECT * FROM orders
WHERE salesman_id = 5001;

SELECT * FROM orders
WHERE salesman_id IN (
		SELECT salesman_id
        FROM salesman
		WHERE city = 'New York');
/*
# ord_no, purch_amt, ord_date, customer_id, salesman_id
'70002', '65.26', '2012-10-05', '3002', '5001'
'70005', '2400.60', '2012-07-27', '3007', '5001'
'70008', '5760.00', '2012-09-10', '3002', '5001'
'70013', '3045.60', '2012-04-25', '3002', '5001'
*/
```

#### 6. Write a query to display commission, where salesman_id is in customer from city = 'paris'. (use IN)

```sql

SELECT salesman_id FROM customer
WHERE city = 'Paris'; -- 5006
SELECT commission FROM salesman
WHERE salesman_id = 5006; -- 0.14

SELECT commission FROM salesman
WHERE salesman_id IN (
		SELECT salesman_id
        FROM customer
		WHERE city = 'Paris');


```

#### 7. Write a query to count the customers with grades above new-york's avg grade.

```sql
SELECT AVG(grade) FROM customer
WHERE city = 'New York'; -- '150.0000'
SELECT COUNT(*) FROM customer
WHERE grade > 150; -- 5

SELECT COUNT(*) FROM customer
WHERE grade > (
		SELECT AVG(grade)
        FROM customer
		WHERE city = 'New York'
); -- 5
```
