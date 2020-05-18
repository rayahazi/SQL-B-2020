```sql

CREATE TABLE Customers(
	customer_id INT PRIMARY KEY,
    full_name NVARCHAR(20) NOT NULL,
    country NVARCHAR(20) NOT NULL
);


CREATE TABLE Orders(
	order_id INT PRIMARY KEY,
    customer_id INT,
    order_date DATE,
    FOREIGN KEY(customer_id) REFERENCES Customers(customer_id)
);
```

```sql
INSERT INTO Customers(customer_id, full_name, country)
VALUES  (1, 'Bob', 'Israel'),
		(2, 'Alice', 'Brazil'),
		(3, 'John', 'Canada'),
		(4, 'Jennifer', 'USA');

INSERT INTO Orders(order_id, customer_id, order_date)
VALUES  (1, 3, '2020-05-04'),
		(2, 2, '2020-02-01'),
        (3, 1, '2019-12-21'),
        (4, 2, '2018-03-29');

```

## Join - Inner join

Inner join is the standard for joining two or more tables.

```sql
SELECT Orders.order_id, Customers.full_name, Orders.customer_id
FROM Orders
INNER JOIN Customers
ON Orders.customer_id = Customers.customer_id
```

## Left join

```sql
SELECT Customers.full_name, Orders.order_date
FROM Orders
LEFT JOIN Customers
ON Orders.customer_id = Customers.customer_id
ORDER BY Customers.full_name

```

```sql
# full_name, order_date
'Alice', '2020-02-01'
'Alice', '2018-03-29'
'Bob', '2019-12-21'
'John', '2020-05-04'
```

```sql
SELECT Customers.full_name, Orders.order_date
FROM Customers
LEFT JOIN Orders
ON Orders.customer_id = Customers.customer_id
ORDER BY Customers.full_name
```

or:

```sql

SELECT c.full_name, o.order_date
FROM Customers as c
LEFT JOIN Orders as o
ON o.customer_id = c.customer_id
ORDER BY c.full_name
```

```sql
# full_name, order_date
'Alice', '2020-02-01'
'Alice', '2018-03-29'
'Bob', '2019-12-21'
'Jennifer', NULL
'John', '2020-05-04'

```

## RIGHT JOIN

```sql
SELECT o.order_date, c.full_name
FROM Customers as c
RIGHT JOIN Orders as o
ON o.customer_id = c.customer_id
ORDER BY c.full_name
```

```sql
# order_date, full_name
'2020-02-01', 'Alice'
'2018-03-29', 'Alice'
'2019-12-21', 'Bob'
'2020-05-04', 'John'
```

```sql
SELECT c.full_name, o.order_date
FROM Orders as o
RIGHT JOIN Customers as c
ON o.customer_id = c.customer_id
ORDER BY c.full_name
```

```sql
# full_name, order_date
'Alice', '2018-03-29'
'Alice', '2020-02-01'
'Bob', '2019-12-21'
'Jennifer', NULL
'John', '2020-05-04'
```
