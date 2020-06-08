# Stored procedures:

- Select from table `salesman` where city is x or y.
  we created abstract procedure (we can use in the procedure each time with diffrent variables).

```sql
use class;

SET @city1 = 'London', @city2 = 'Paris';

CREATE PROCEDURE selectCity(x NVARCHAR(20), y NVARCHAR(20))
	SELECT * FROM salesman
    WHERE city = x OR city = y;

CALL selectCity(@city1, @city2);
CALL selectCity('New york', @city2);
CALL selectCity('New york', 'London');
```

### SHOW PROCEDURE status;

```sql
# Db, Name, Type, Definer, Modified, Created, Security_type, Comment, character_set_client, collation_connection, Database Collation
'class', 'selectByCity', 'PROCEDURE', 'root@localhost', '2020-06-08 09:18:57', '2020-06-08 09:18:57', 'DEFINER', '', 'utf8', 'utf8_general_ci', 'latin1_swedish_ci'
'class', 'selectCity', 'PROCEDURE', 'root@localhost', '2020-06-08 09:13:04', '2020-06-08 09:13:04', 'DEFINER', '', 'utf8', 'utf8_general_ci', 'latin1_swedish_ci'
'class', 'showSalesman', 'PROCEDURE', 'root@localhost', '2020-06-01 10:46:46', '2020-06-01 10:46:46', 'DEFINER', '', 'utf8', 'utf8_general_ci', 'latin1_swedish_ci'
'class', 'showSalesmanLimit', 'PROCEDURE', 'root@localhost', '2020-06-01 11:20:09', '2020-06-01 11:20:09', 'DEFINER', '', 'utf8', 'utf8_general_ci', 'latin1_swedish_ci'
```

### DROP PROCEDURE selectByCity;

```sql
# Db, Name, Type, Definer, Modified, Created, Security_type, Comment, character_set_client, collation_connection, Database Collation
'class', 'selectCity', 'PROCEDURE', 'root@localhost', '2020-06-08 09:13:04', '2020-06-08 09:13:04', 'DEFINER', '', 'utf8', 'utf8_general_ci', 'latin1_swedish_ci'
'class', 'showSalesman', 'PROCEDURE', 'root@localhost', '2020-06-01 10:46:46', '2020-06-01 10:46:46', 'DEFINER', '', 'utf8', 'utf8_general_ci', 'latin1_swedish_ci'
'class', 'showSalesmanLimit', 'PROCEDURE', 'root@localhost', '2020-06-01 11:20:09', '2020-06-01 11:20:09', 'DEFINER', '', 'utf8', 'utf8_general_ci', 'latin1_swedish_ci'

```

### Create full procedure:

```sql
use class;

DELIMITER //

CREATE PROCEDURE selectById()
	BEGIN
	SELECT * FROM customer
    WHERE customer_id > 3005;
    END //

CALL selectById();
```

- Output:

```sql
# customer_id, cust_name, city, grade, salesman_id
'3007', 'Brad Davis', 'New York', '200', '5001'
'3009', 'Geoff Cameron', 'Berlin', '100', '5003'
'3008', 'Julian Green', 'London', '300', '5002'
```

- valid:

```sql
DELIMITER $$
CREATE PROCEDURE selectById()
	BEGIN
	SELECT * FROM customer
    WHERE customer_id > 3005;
    END $$
```

## IN

- IN is the default state for parameters in procedure.
- IN passes to the procedure by value type.

```sql
use class;

SET @var1 = 3003;

SELECT @var1;

DELIMITER $$
DROP PROCEDURE IF EXISTS showIn;
CREATE PROCEDURE showIn(IN x INT)
	BEGIN
    -- declare variables:
    SET x = 10;
    SELECT x;
    END $$

CALL showIn(@var1);
SELECT @var1;

```

- Memory image: if we change the value of x - the value of @var1 does not change.

```
@var1 = 3003;
x = 3003;
x = 10;
```

## OUT

```sql
use class;

SET @var1 = 3005;

DELIMITER $$
DROP PROCEDURE IF EXISTS showOut;
CREATE PROCEDURE showOut(OUT varNew INT)
	BEGIN
    -- declare variables:
    SET varNew = 10;
    SELECT varNew;
    END $$

CALL showOut(@var1);
SELECT @var1;
```

- Memory image: if we change the value of x - the value of @var1 does not change.

```
@var1 = 3003;
x = 3003;
x = 10;
```

### IN:

```sql
use class;
-- IN
SET @city = 'London';
SET @x = @city;

SELECT @city, @x;

SET @x = 'Paris';

SELECT @city, @x;

SET @city = 'Haifa';

SELECT @city, @x;
```
