# Syntax - תחביר
All saved words are in blue, and upper-case(not must). 
; in the end of command. 

# DDL + DML
### what is DDL - data definition language: 
כל הפקודות שאחראיות לבניית מסד-הנתונים והטבלאות. 
* DDL:
```
    CREATE
    ALTER
    DROP
```
### what is DML - data manipulation language: 
כל הפקודות שקשורות להכנסת מידע, לבחירת מידע, לעדכון ולמחיקה. 
* DML:
```
    SELECT
    INSERT
    UPDATE
    DELETE
```

## First commands 
DDL:
* CREATE DATABASE
* use database;
* DROP DATABASE
* CREATE TABLE
* TRUNCATE TABLE table_name;  - truncate: delete all the data from table, but keeps the table. 
* DROP TABLE                  - drop: delete all the data. including the table itself. 

### Select *
*= all

```sql
SELECT * FROM `table_name`
```
