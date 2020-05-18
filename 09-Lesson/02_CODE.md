## ONE-TO-MANY

```sql
-- one to many relationship:
CREATE TABLE city(
	city_id INT PRIMARY KEY,
    name VARCHAR(20) NOT NULL,
    population INT
);

CREATE TABLE cinema(
	cinema_id INT PRIMARY KEY,
    city_id INT,
    cinema_name VARCHAR(20) NOT NULL,
    FOREIGN KEY(city_id) REFERENCES city(city_id)
);

INSERT INTO city(city_id, name, population)
VALUES (1,'Jerusalem', 100000),(2,'Tel-aviv', 200000);

INSERT INTO cinema(cinema_id, city_id, cinema_name)
VALUES (1, 2, 'a'), (2, 2, 'b') ;
```

## MANY-TO-MANY

```sql

USE mydb;


CREATE TABLE book(
	book_id INT PRIMARY KEY,
    book_name VARCHAR(20),
    num_of_pages INT
);

CREATE TABLE publisher(
	publisher_id INT PRIMARY KEY,
    publisher_name VARCHAR(20),
    country VARCHAR(20)
);


CREATE TABLE book_publisher(
	id INT PRIMARY KEY,
	publisher_id INT,
    book_id INT,
    FOREIGN KEY (publisher_id) REFERENCES publisher(publisher_id),
    FOREIGN KEY (book_id) REFERENCES book(book_id)
);

INSERT INTO book(book_id, book_name,num_of_pages)
VALUES (1,'a', 10),(2,'b', 20),(3,'c', 200);

INSERT INTO publisher(publisher_id, publisher_name,country)
VALUES (1,'Bob', 'USA'),(2,'Alice', 'Poland'),(3,'Chris', 'Belgium');

INSERT INTO book_publisher(id, publisher_id, book_id)
VALUES (1, 1, 3),(2,1, 1),(3,3, 1);

SELECT * FROM book_publisher;

```
