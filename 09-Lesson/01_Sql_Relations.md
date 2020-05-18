# Relations:

Types of Relationships
a. One-to-One Relationship (1-1 Relationship)
b. One-to-Many Relationship (1-M Relationship)
c. Many-to-Many Relationship (M-M Relationship)

## a. One-to-One Relationship

In Databases, One-to-one relationship occurs when there is exactly one record in the parent table that corresponds to exactly one record in the child table. this kind of relationship is not very common.

- One employee belongs to one organization.

- One dog belongs to one person (or one family).

- One person has one passport.

- A car model is made by one company.

* Example:
  <img src="https://www.techalyst.com/content/uploads/editor-photos/blog/b76e002b8e75770a5171c6ad576cffbe92b68ad7.png"/>

## b. One-to-Many Relationship

- one Writer can have many books.

- Example: One customer can have many orders.

  <img src="https://cdn.tutsplus.com/net/uploads/
  legacy/538_sql3/ss_6.png"/>

* Example: One city can have many cinemas.
  <img src="https://i.stack.imgur.com/mQQlj.png"/>

* Code example:

```sql
create table customer(
ID int primary key auto_increment,
Full_Name nvarchar(20) not null,
Address nvarchar(20)
);

create table orders(
ID int primary key auto_increment,
Order_date datetime,
amount int,
CustomerId int,
foreign key (CustomerId) references customer(ID)
);
```

## c. Many-to-Many Relationship

- A student can register for many classes, and a class can include many students.
  <img src="https://hellokoding.com/content/images/2019/02/Screenshot-2019-02-01-at-10-26-21-AM.png"/>

<img src="https://i.stack.imgur.com/kn5nB.png"/>

<img src="https://fmhelp.filemaker.com/help/18/fmp/en/FMP_Help/images/relational.07.06.1.png">

