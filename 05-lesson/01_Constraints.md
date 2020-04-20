
## CHECK - Ensures that all values in a column satisfies a specific condition
The CHECK constraint is used to limit the value range that can be placed in a column.

If you define a CHECK constraint on a single column it allows only certain values for this column.

If you define a CHECK constraint on a table it can limit the values in certain columns based on values in other columns in the row.
```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CHECK (Age>=18)
);
```

To allow naming of a CHECK constraint, and for defining a CHECK constraint on multiple columns:
```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255),
    CONSTRAINT CHK_Person CHECK (Age>=18 AND City='Sandnes')
);
```
in alter:
```sql
ALTER TABLE Persons
ADD CHECK (Age>=18);
```
drop check:
```sql
ALTER TABLE Persons
DROP CHECK CHK_PersonAge;
```
## DEFAULT - Sets a default value for a column when no value is specified
The DEFAULT constraint is used to provide a default value for a column.

The default value will be added to all new records IF no other value is specified.
```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255) DEFAULT 'Sandnes'
);
```
in alter:
```sql
ALTER TABLE Persons
ALTER City SET DEFAULT 'Sandnes';
```
in drop:
```sql
ALTER TABLE Persons
ALTER City DROP DEFAULT;
```

## AUTO INCREMENT
Auto-increment allows a unique number to be generated automatically when a new record is inserted into a table.

Often this is the primary key field that we would like to be created automatically every time a new record is inserted.
```sql
CREATE TABLE Persons (
    Personid int NOT NULL AUTO_INCREMENT,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (Personid)
);
```
Change the start (to 100).
```sql
ALTER TABLE Persons AUTO_INCREMENT=100;
```

