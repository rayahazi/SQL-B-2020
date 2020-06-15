# Calculation functions

## ABS(x) 
Returns the absolute (מוחלט) value of x. 
```sql 
SELECT ABS(2);   -- 2
SELECT ABS(-24); -- 24
```
## CEILING(x) - תקרה
Returns the smallest integer value not less than x. 
```sql
SELECT CEILING(1.45);  -- (2)
SELECT CEILING(-1.45); -- (-1)
```
## FLOOR(x) - רצפה
Returns the largest integer value not greater than x. 
```sql
SELECT FLOOR(1.25);  -- 1
SELECT FLOOR(-1.25); -- (-2) 
```

## ROUND(x) - עיגול
Returns the rounded value of `x`. 

If `x` is equal or greater than `0.5` - rounded to the next number. else - rounded to the smaller number. 
```sql
SELECT ROUND(-1.23); -- (-1)
SELECT ROUND(1.5);   -- 2
```
## PI - Constant number. 
```sql
SELECT PI(); -- '3.141593'
```

## POW(x, y) - power - חזקה
Returns the value of `x` raised to the power of `y`


```sql
SELECT POW(2, 3);  -- 8
SELECT POW(4, -2); -- '0.0625'
```

## SQRT(x) - square root - שורש
Returns the square root of non - negative `x`
```sql
SELECT SQRT(9);   -- 3
SELECT SQRT(20);  -- '4.47213595499958'
SELECT SQRT(-13); -- null
```
#### Use the functions on a column:
this function does not change the actual value of the data in this column
```sql
select id,floor(val) from z;
```
