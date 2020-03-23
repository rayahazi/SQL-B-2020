# Class task
* Create Database name: `Mall`
* Create table name: `FoodStore`
with columns: Id, name, category, amount, price, expiration_date. 

* Create table name: `MallSecurity`
with columns: Id, name, role, IsMale, salary, hoursPerMonth

Note: all columns must be with the right data types. 


# Answer for class task:
1. Create new database:
```sql
CREATE DATABASE Mall;
```
2. Create table `FoodStore`
```sql
USE Mall;

CREATE TABLE FoodStore(
	ID 		 INT, 
    FullName NVARCHAR(20),
    Category NVARCHAR(20),
    Amount 	 INT, 
    Price    FLOAT, 
    Expiration_date DATE
);
```

2. Create table `MallSecurity`
```sql
USE Mall;

CREATE TABLE MallSecurity(
	ID int,
    Name NVARCHAR(20),
    Role NVARCHAR(20),
    IsMale BOOLEAN,
    Salary FLOAT, 
    HoursPerMonth FLOAT
);
```
