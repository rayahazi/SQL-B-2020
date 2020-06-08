# class task

- Create 2 varialbes: `city` = 'London', `id` = 3002
- Create procedure that gets 2 variables, city and id.
  it will get city as `in` and id as `in`.

##### In the procedure

- In the procedure - create a statement that uses the two variables to select all the users that are from `city`, and their id is bigger than the `id`.
- change the values of city = "Paris" and id = "3008".
- print the new values.

##### Outside

- Outside the procedure: call it with the two variables.
- print the two values of city and id.

```sql
use class;

SET @city = 'London', @id = 3002;

DELIMITER $$
DROP PROCEDURE IF EXISTS getRes;
CREATE PROCEDURE getRes(IN city_var nvarchar(20), OUT id_var INT)
	BEGIN

    -- select data from customer using the 2 variables:
    SELECT * FROM customer
	WHERE city = city_var and customer_id > id_var;

    -- change values:
    SET city_var = 'Paris', id_var = 3008;
    SELECT city_var, id_var;
    END $$

CALL getRes(@city, @id);

-- # city_var, id_var
-- 'Paris', '3008'


SELECT @city, @id;
-- # city_var, id_var
-- London, 3008
```