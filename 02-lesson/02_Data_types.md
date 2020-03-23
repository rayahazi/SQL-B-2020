# MySQL: Data Types
<div dir=rtl>
  
  ## סוג טיפוס: מחרוזות:
  `CHAR` - תו. תופס בזיכרון בדיוק את כל המקום שהגדרנו לו. צריך להגדיר את האורך. 
  יגדיר מקום בזיכרון בדיוק כפי שהגדרנו לו. 
   ```sql
      column_name CHAR(4)
   ```
  `VARCHAR` - מחרוזת. צריך להגדיר את אורך המחרוזת.
    יגדיר מקום בזיכרון על פי מה שהכנסו לתוכו. אם הכנסנו ערך שלא תופס את כל המקום, אז כך זה יראה.  
   ```sql
      column_name VARCHAR(20)
   ```
   
  `NVARCHAR` -  מחרוזת שכוללת שפות נוספות. כמו עברית. משתמשת בטבלת Unicode
   ```sql
       column_name NVARCHAR(20)
   ```
  
   ## סוג טיפוס: מספרים:
   `BIT` - . טווח: 1-64 ביט. ערך בינארי. של אפסים ואחדות
 ```sql
   column_name BIT;
   or:
   column_name BIT(1);
   
   ```
   `INT` - (integer) - מספר שלם. זהו הערך הסטנדרטי עבור מספרים. גודלו: 4 בייט. 
```sql
   column_name INT;
   ```
   `FLOAT` - מספר צף. בעל נקודה עשרונית. גודלו: 4 בייט.
   דוגמא: 4.5
 ```sql
   column_name FLOAT;
   
   ```
   `DOUBLE` - מספר צף. גודלו: 8 בייט.
```sql
   column_name DOUBLE;
   
   ```
   `BOOLEAN` - יכול להיות רק 2 אפשרויות: אמת או שקר. 
   `true` / `false`:
```sql
   column_name DOUBLE;
  ```
  
  `DATE` - 'YYYY-MM-DD' : שנה, חודש, ויום. 
 ```sql
   column_name DATE;
  ```
  
  `TIME` - 'HH-MM-SS': שעות, דקות, שניות. 
  ```sql
   column_name TIME;
  ```
 
  
  `DATETIME`  - 'YYYY-MM-DD:HH-MM-SS' : שנה, חודש, ויום. 
    ```sql
   column_name DATETIME;
  ```
  
  
  
  
  </div>


The following is a list of datatypes available in MySQL, which includes string, numeric, date/time, and large object datatypes.

## String Datatypes

The following are the **String Datatypes** in MySQL:

| Data Type Syntax   | Maximum Size                                     | Explanation                                                                                                                                                          |
| ------------------ | ------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `CHAR(size)`       | Maximum size of 255 characters.                  | A FIXED length string (can contain letters, numbers, and special characters). The size parameter specifies the column length in characters - can be from 0 to 255. Default is 1                                      |
| `VARCHAR(size)`    | Maximum size of 255 characters.                  | A VARIABLE length string (can contain letters, numbers, and special characters). The size parameter specifies the maximum column length in characters - can be from 0 to 65535      
| `NCHAR(size)`      | Maximum size of 255 characters.                  | Fixed width Unicode string	                                   
| `NVARCHAR(size)`    | Maximum size of 255 characters.                  | Where **size** is the number of characters to store. 


## Numeric Datatypes

The following are the **Numeric Datatypes** in MySQL:

| Data Type Syntax        | Maximum Size                                                                                                                            | Explanation                                                                                                                                                   |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `BIT`                   | Very small integer value that is equivalent to `TINYINT(1)`. Signed values range from -128 to 127. Unsigned values range from 0 to 255. |
| `TINYINT(m)`            | Very small integer value. Signed values range from -128 to 127. Unsigned values range from 0 to 255.                                    |
| `SMALLINT(m)`           | Small integer value. Signed values range from -32768 to 32767. Unsigned values range from 0 to 65535.                                   |
| `MEDIUMINT(m)`          | Medium integer value. Signed values range from -8388608 to 8388607. Unsigned values range from 0 to 16777215.                           |
| `INT(m)`                | Standard integer value. Signed values range from -2147483648 to 2147483647. Unsigned values range from 0 to 4294967295.                 |
| `BIGINT(m)`             | Big integer value. Signed values range from -9223372036854775808 to 1. Unsigned values range from 0 to 18446744073709551615.            |
| `DECIMAL(m,d)`          | Unpacked fixed point number. `m` defaults to 10, if not specified. `d` defaults to 0, if not specified.                                 | Where `m` is the total digits and `d` is the number ofdigits after the decimal.                                                                               |
| `FLOAT(m,d)`            | Single precision floating point number.                                                                                                 | Where `m` is the total digits and `d` is the number ofdigits after the decimal.                                                                               |
| `DOUBLE(m,d)`           | Double precision floating point number.                                                                                                 | Where `m` is the total digits and `d` is the number ofdigits after the decimal.                                                                               |
| `BOOLEAN`               | Synonym for `TINYINT(1)`                                                                                                                | Treated as a boolean data type where a value of 0 is considered to be `FALSE` and any other value isconsidered to be `TRUE`.                                  |


## Date/Time Datatypes

The following are the **Date/Time Datatypes** in MySQL:

| Data Type Syntax | Maximum Size                                                              | Explanation                         |
| ---------------- | ------------------------------------------------------------------------- | ----------------------------------- |
| `DATE`           | Values range from '1000-01-01' to '9999-12-31'.                           | Displayed as 'YYYY-MM-DD'.          |
| `DATETIME`       | Values range from '1000-01-01 00:00:00' to '9999-12-31 23:59:59'.         | Displayed as 'YYYY-MM-DD HH:MM:SS'. |
| `TIMESTAMP(m)`   | Values range from '1970-01-01 00:00:01' UTC to '2038-01-19 03:14:07' UTC. | Displayed as 'YYYY-MM-DD HH:MM:SS'. |
| `TIME`           | Values range from '-838:59:59' to '838:59:59'.                            | Displayed as 'HH:MM:SS'.            |
| `YEAR[(2\|4)]`    | Year value as 2 digits or 4 digits.                                       | Default is 4 digits.                |

