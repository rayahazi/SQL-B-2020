# Class task joins:

```sql
create database class;
use class; 

CREATE TABLE salesman (
    salesman_id int NOT NULL,
    name  nvarchar(30) NOT NULL,
    city  nvarchar(15),
    commission numeric(5,2)
);

use class; 
insert into  salesman (salesman_id, name, city, commission)
values
(5001,	'James Hoog',	'New York',	0.15),
(5002,	'Nail Knite',	'Paris',	0.13),
(5005,	'Pit Alex',	'London',	0.11),
(5006,	'Mc Lyon',	'Paris',	0.14),
(5007,	'Paul Adam',	'Rome',	0.13),
(5003,	'Lauson Hen'	,'San Jose',	0.12);


CREATE TABLE orders (
    ord_no numeric(5,0) NOT NULL,
    purch_amt numeric(8,2) DEFAULT 0,
    ord_date date,
    customer_id numeric(5,0) NOT NULL,
    salesman_id numeric(5,0) NOT NULL
);


INSERT INTO orders (ord_no, purch_amt, ord_date, customer_id, salesman_id) VALUES
(70009,	270.65,	'2012-09-10',	3001,	5005),
(70002	,65.26	,'2012-10-05',	3002,	5001),
(70004	,110.50	,'2012-08-17'	,3009	,5003),
(70005,	2400.60	,'2012-07-27'	,3007	,5001),
(70008,	5760.00	,'2012-09-10'	,3002	,5001),
(70010,	1983.43	,'2012-10-10',	3004,	5006),
(70003	,2480.40,	'2012-10-10',	3009,	5003),
(70011	,75.29	,'2012-08-17',	3003,	5007),
(70013	,3045.60,	'2012-04-25',	3002,	5001),
(70001	,150.50	,'2012-10-05',	3005,	5002),
(70007	,948.50	,'2012-09-10'	,3005	,5002),
(70012	,250.45	,'2012-06-27'	,3008	,5002);

CREATE TABLE customer (
    customer_id int NOT NULL,
    cust_name  nvarchar(30) NOT NULL,
    city  nvarchar(15),
    grade int DEFAULT 0,
    salesman_id int NOT NULL
);


INSERT INTO customer (customer_id, cust_name, city, grade, salesman_id) values
(3002,	'Nick Rimando',	'New York',	100		,5001),
(3007,	'Brad Davis',	'New York'	,200	,5001),
(3005,	'Graham Zusi',	'California',200    ,5002),
(3008,	'Julian Green'	,'London'	,300	,5002),
(3004,	'Fabian Johnson','Paris'	,300	,5006),
(3009,	'Geoff Cameron','Berlin'	,100	,5003),
(3003,	'Jozy Altidor','Moscow'	,200	,5007),
(3001,	'Brad Guzan',	'London',100,	5005);

```
# Questions

1. Write a SQL statement to prepare a list with salesman name, customer name and their cities for the salesmen and customer who belongs to the same city. 

2. Write a SQL statement to make a list with order no, purchase amount, customer name and their cities for those orders which order amount between 500 and 2000. 


3. Write a SQL statement to know which salesman are working for which customer. 

4. Write a SQL statement to find the list of customers who appointed a salesman for their jobs who gets a commission from the company is more than 12%.  

5. Write a SQL statement to find the list of customers who appointed a salesman for their jobs who does not live in the same city where their customer lives, and gets a commission is above 12% .  

6. Write a SQL statement to find the details of a order i.e. order number, order date, amount of order, which customer gives the order and which salesman works for that customer and how much commission he gets for an order.  

7. Write a SQL statement to make a list in ascending order for the customer who works either through a salesman or by own.  

8. Write a SQL statement to make a list in ascending order for the customer who holds a grade less than 300 and works either through a salesman or by own. 

9. Write a SQL statement to make a report with customer name, city, order number, order date, and order amount in ascending order according to the order date to find that either any of the existing customers have placed no order or placed one or more orders. 

10. Write a SQL statement to make a report with customer name, city, order number, order date, order amount salesman name and commission to find that either any of the existing customers have placed no order or placed one or more orders by their salesman or by own. 

11. Write a SQL statement to make a list in ascending order for the salesmen who works either for one or more customer or not yet join under any of the customers. 

12. Write a SQL statement to make a list for the salesmen who works either for one or more customer or not yet join under any of the customers who placed either one or more orders or no order to their supplier. 

