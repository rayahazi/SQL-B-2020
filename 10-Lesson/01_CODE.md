# Lesson 10

- Write query to display all orders from the table, that connected to salesman - `Paul Adam`

```sql
use class;

select * from orders
where salesman_id =
		(select salesman_id
        from salesman
        where name = 'Paul Adam');

-- 70011	75.29	2012-08-17	3003	5007
```

- Write query to display all orders from the table, that belong to salesman from London

```sql
use class;

select * from orders
where salesman_id =
		(select salesman_id
        from salesman
        where city = 'London');
-- 70009	270.65	2012-09-10	3001	5005
```

- Write query to display all orders from the table, that belong to customer_id = 3007
  > note: This code is exacly the same:

```sql

select * from orders
where salesman_id = 5001;

select * from orders
where salesman_id =(select salesman_id
        from orders
        where customer_id = 3007);
```

- Result:

```sql

# ord_no, purch_amt, ord_date, customer_id, salesman_id
-- 70002	65.26	2012-10-05	3002	5001
-- 70005	2400.60	2012-07-27	3007	5001
-- 70008	5760.00	2012-09-10	3002	5001
-- 70013	3045.60	2012-04-25	3002	5001
```

- Write query to display all orders, where purch_amt is greater than the average of purc_amt from date: '2012-04-25'

```sql

select * from orders
where purch_amt >
	(select avg(purch_amt) from orders
      where ord_date = '2012-04-25'
    );
```

- Result:

```sql
# ord_no, purch_amt, ord_date, customer_id, salesman_id
'70008', '5760.00', '2012-09-10', '3002', '5001'
```

- Write query to display all orders, where salesman is from 'New York' (use IN)

```sql
select * from orders
where salesman_id in (5001);

select * from orders
where salesman_id in (
		select salesman_id from salesman
        where city = 'New York');
```

- Write query to display commission, where salesman_id is in customer - from city = 'Paris'
  (use IN)

```sql
select commission from salesman
where salesman_id in (
		select salesman_id from customer
        where city = 'Paris');
-- 0.14
```

- Write query to count the customers with grades above New yourk's avg grade.

```sql
select * from customer;

select grade, count(*)
from customer
where grade > (
		select avg(grade) from customer
        where city = 'New York');
```

- Result:

```sql
-- # grade, count(*)
'200', '5'
```
