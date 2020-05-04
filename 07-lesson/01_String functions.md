# String functions

## ASCII()

Returns the numeric value of the leftmost charaacter of the string.

If string is empty - will return 0.
If string is NULL - will return NULL.

```sql
SELECT ASCII('2');  -- 50

SELECT ASCII('sql'); -- 115. `s` is 115 in decimal value.
```

## BIN()

Returns the string representation of the binary value of `N`.

```
SELECT BIN(N);
```

```sql
SELECT BIN(12); -- '1100'

SELECT BIN(432); -- '110110000'
```

## CHAR(str), CHAR(N)

CHAR() converts each `N` as an integer and returns a string according to it's ASCII value.

```sql
SELECT CHAR(77, 121, 83, 81, '76'); -- MySql
```

## CONCAT()

Returns the string that results from concatenating the arguments.

If there is NULL in one of the arguments - will return NULL.

```sql
SELECT CONCAT('MY','S','QL');  -- MYSQL
SELECT CONCAT('MY',NULL,'QL'); -- NULL
SELECT CONCAT(14.3); 		   -- '14.3'

```

## HEX(str), HEX(N)

Returns the hexadecimal string representation of `str`.

```sql
SELECT HEX('abc');   -- 616263
SELECT X'616263';    -- abc
SELECT HEX(255); 	 -- FF
```

## LENGTH(str)

Returns the length of a string `str`.

```sql
SELECT LENGTH('text');  -- 4
SELECT LENGTH('MySql'); -- 5
```

## LOWER(str)

Returns the string `str` with all characters changed to lowercase according to the current chararcter ASCII value.

```sql
SELECT LOWER('THIS IS A SENTENCE'); -- 'this is a sentence'
SELECT LOWER('MySql');				-- 'mysql'
```

## UPPER(str)

Returns the string `str` with all characters changed to uppercase according to the current chararcter ASCII value.

```sql
SELECT UPPER('this is a sentence'); -- 'THIS IS A SENTENCE'
SELECT UPPER('MySql');				-- 'MYSQL'

```

## REPEAT(str, )count

Returns the string `str` repeated `count` times.
If `count` is less than 1, returns an empty string.

```sql
SELECT REPEAT('MySql', 3); -- 'MySqlMySqlMySql'
SELECT REPEAT('Word', -5); -- empty string
```

## REPLACE(str, from_str, to_str)

Returns the string `str` with all occurences of the string `from_str` replaced with `to_str`.

```sql
SELECT REPLACE('www.mysql.com','w','W');    -- 'WWW.mysql.com'
SELECT REPLACE('Sunday morning','Su','Mo'); -- 'Monday morning'
SELECT REPLACE('Sunday Sunday','Su','Mo');  -- 'Monday Monday'
```

## REVERSE(str)

Returns the string `str` with the order of the characters reversed.

```sql
SELECT REVERSE('abcd');        -- 'dcba'
SELECT REVERSE('Hello World'); -- 'dlroW olleH'

```

## SUBSTRING(str, position), SUBSTRING(str, position, len)

> note: the count of the `position` starts from 1.
> note: the count will include the number(and from the number).

**SUBSTRING(str, position)** - Returns the substring `str` according to `position` value.
**SUBSTRING(str, position, len)** - Returns the substring `str` according to `position` value, with the length of `len` value.

If `-` is used - substring will start from the end of the string.

```sql
SELECT SUBSTRING('Hello World', 6);      -- World
SELECT SUBSTRING('Lesson07', 7);         -- 07
SELECT SUBSTRING('Beautiful day',7, 3 )  -- ful
SELECT SUBSTRING('Beautiful day', -3); 	 -- day
```
