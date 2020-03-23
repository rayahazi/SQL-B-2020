# Syntax
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
* TRUNCATE TABLE table_name;
* DROP TABLE

### data types
int, varchar, nvarchar, boolean, float, double, 
full list is in separated page. 

```
להדגים איך יוצרים מסד נתונים וטבלה עם טורים
```

### task A
* Create DB name: `University`
* Create table name: `ClassA`
* Columns: ID, FirstName, LastName, BirthDate, AvgGrades, PhoneNumber. 
with the right data types. 
* Execute command

### Select *
*= all

```sql
SELECT * FROM `ClassA`
```
