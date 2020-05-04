# Date functions

### CURDATE()

Returns the current date. format: 'YYYY:MM:DD'

```sql
SELECT CURDATE(); -- '2020-05-04'
```

### CURTIME()

Returns the current time. format: 'HH:MM:SS'

```sql
SELECT CURTIME(); -- '10:37:25'
```

### DATE(expr)

Extract the date part of the date datetime expression `expr`

```sql
SELECT DATE('2003-12-29'); 			-- '2003-12-29'
SELECT DATE('2003-12-29 01:02:03'); -- '2003-12-29'
```

### DATEDIF(expr1, expr2)

Returns `expr1 - expr2`. the amount of gap between 2 dates in days.

```sql
SELECT DATEDIFF('2020-05-04','2020-05-02'); -- 2
```

### DATE_ADD(expr, INTERVAL `time`), DATE_SUB(expr, INTERVAL `time`)

Returns the date with intervals of add / sub from that day.
We can use: DAY, MONTH, YEAR.

> note: we can use any interval nubmer.

```sql
SELECT DATE_ADD('2020-05-04', INTERVAL 1 DAY);  -- '2020-05-05'
SELECT DATE_ADD('2020-05-04', INTERVAL 10 DAY); -- '2020-05-14'
SELECT DATE_ADD('2020-05-04', INTERVAL 1 YEAR); -- '2021-05-04'

SELECT DATE_SUB('2020-05-04', INTERVAL 1 DAY);  -- '2021-05-03'
SELECT DATE_SUB('2020-05-04', INTERVAL 1 YEAR); -- '2019-05-04'
```

### DAYNAME(date)

Returns the name of the weekday for `date`. Range: 1-7 options. (for week days). string value.

```sql
SELECT DAYNAME('2020-05-04'); -- 'Monday'
SELECT DAYNAME('2020-05-06'); -- 'Wednesday'
```

### DAYOFWEEK(date)

Returns the name of the weekday for `date`. Range: 1-7 options. (for week days). Numeric value.

```sql
SELECT DAYOFWEEK('2020-05-04'); -- 2
```

### DAYOFMONTH(date)

Returns the day of the month for `date`. Range: 1-31.

```sql
SELECT DAYOFMONTH('2020-05-04'); -- 4
SELECT DAYOFMONTH('0000-00-00'); -- 0
```

### HOUR(time)

Returns the hour of `time`. Range: 0-23.
(The range of HOUR is much larger than 23)

```sql
SELECT HOUR('10:05:03');  -- 10
SELECT HOUR('274:05:03'); -- 274
SELECT HOUR('54274:05:03'); -- 838
```

### MINUTE(time)

Returns the minutes of `time`. Range: 0-59.

```sql
SELECT MINUTE('10:05:03');  -- 5
SELECT MINUTE('10:95:03'); -- NULL
```

### MONTH(date)

Returns the month of `date`.

```sql
SELECT MONTH('2003-02-12'); -- 2
```

### MONTHNAME(date)

Returns the full name of the month for `date`.

```sql
SELECT MONTHNAME('2003-02-12'); -- 'February'
```

### NOW()

Returns the current date and time. 'YYYY:MM:DD hh:mm:ss' format.

```sql
SELECT NOW(); -- '2020-05-04 11:02:54'

```

###### NOW() vs SYSDATE()

NOW() returns a constant time. (represent the time which the statement began to execute).
SYSDATE() is diffrent than NOW(), which returns the exact time at which it executed.

```sql
SELECT NOW(), SLEEP(3), NOW();
-- '2020-05-04 11:04:06', '0', '2020-05-04 11:04:06'

SELECT SYSDATE(), SLEEP(3), SYSDATE();
-- '2020-05-04 11:05:58', '0', '2020-05-04 11:06:01'

```

### SECOND(time)

Returns the seconds for `time`. Range: 0-59.

```sql
SELECT SECOND('10:46:37'); -- 37
SELECT SECOND('10:46:61'); -- NULL
```

### TIME(expr)

Returns the time of `expr`

```sql
SELECT TIME('01:02:03'); 			-- '01:02:03'
SELECT TIME('2003-12-29 01:02:03'); -- '01:02:03'
```

### WEEK(date)

Returns the number of weeks from the beginning of the year for `date`. Range: 0-53

```sql
SELECT WEEK('2015-01-12'); -- 2
SELECT WEEK('2015-02-12'); -- 6
```

### YEAR(date)

Returns the current year for `date`.
Range: 1000-9999

```sql
SELECT YEAR('2015-12-29'); -- 2015
SELECT YEAR('1676-12-29'); -- 1676
SELECT YEAR('999999-12-29'); -- Null
```
