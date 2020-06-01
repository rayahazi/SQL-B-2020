# Variables in MySql

##### Define variables with the keyword `SET`, and `@` before the name of the variable.

```sql
SET @user_name = 'Brad Guzan';

SELECT @user_name;
```

- numeric values:

```sql
-- numeric variables:
SET @num1 = 4+6;
SET @num2 = @num1 - 3;

SELECT @num1, @num2;
```

#### Use variables in a select statement:

```sql
use class;

SET @amt = 5000;

SELECT * FROM orders
WHERE purch_amt > @amt;
```

- res:

```sql
# ord_no, purch_amt, ord_date, customer_id, salesman_id
'70008', '5760.00', '2012-09-10', '3002', '5001'
'70008', '5760.00', '2012-09-10', '3002', '5001'
'70008', '5760.00', '2012-09-10', '3002', '5001'
```

#### Use := when setting a variable:

```sql
use class;

SET @amt := 2000;

SELECT * FROM orders
WHERE purch_amt > @amt;
```

- res:

```sql
# ord_no, purch_amt, ord_date, customer_id, salesman_id
'70005', '2400.60', '2012-07-27', '3007', '5001'
'70008', '5760.00', '2012-09-10', '3002', '5001'
'70003', '2480.40', '2012-10-10', '3009', '5003'
'70013', '3045.60', '2012-04-25', '3002', '5001'
'70005', '2400.60', '2012-07-27', '3007', '5001'
'70008', '5760.00', '2012-09-10', '3002', '5001'
'70003', '2480.40', '2012-10-10', '3009', '5003'
'70013', '3045.60', '2012-04-25', '3002', '5001'
'70005', '2400.60', '2012-07-27', '3007', '5001'
'70008', '5760.00', '2012-09-10', '3002', '5001'
'70003', '2480.40', '2012-10-10', '3009', '5003'
'70013', '3045.60', '2012-04-25', '3002', '5001'
```

#### Use 2 variables to select specific rows in a table:

```sql

SET @id1 = 70005, @id2 = 70013;

SELECT * FROM orders
WHERE ord_no = @id1 OR ord_no = @id2;
```

- res:

```sql
# ord_no, purch_amt, ord_date, customer_id, salesman_id
'70005', '2400.60', '2012-07-27', '3007', '5001'
'70013', '3045.60', '2012-04-25', '3002', '5001'

```

##### select people from specific cities:

define two variables with `New York` and `Paris`,
and search for any person that lives in this places
in customer table.

```sql
use class;

SET @var1 = 'New York', @var2 = 'Paris';

SELECT * FROM customer
WHERE city = @var1 OR city = @var2;
```

- res:

```sql
# customer_id, cust_name, city, grade, salesman_id
'3002', 'Nick Rimando', 'New York', '100', '5001'
'3007', 'Brad Davis', 'New York', '200', '5001'
'3004', 'Fabian Johnson', 'Paris', '300', '5006'

```
