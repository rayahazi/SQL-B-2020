# Stored procedures

### What is a procedure or function?

- Procedures and functions are very usefull, to avoid repetition of a code.
- Basic functions ic C: printf(), scanf(), main()
- Basic functions ic MySql: concat(), count()

**Parameters**

- Functions can take parameters:

```c
printf("Hello");
```

- Parameters are optional:

```c
void main(){

}
```

### Why use procedure or function?

- Portable
- Always availabe as `source code` in the DB itself.
- fast. (are already in the cache)

SYNTAX:

```sql
CREATE PROCEDURE proc_name(parameters:optional)
	-- code to execute

CALL proc_name(parameters:optional)
```

## Examples:

- Procedure to show all the data in table `salesman`:

```sql

CREATE PROCEDURE showSalesman()
	SELECT * FROM salesman;

CALL showSalesman();
```

- Use variables from the user in the procedure:
- call the procedure each time with diffrent variable.

```sql

CREATE PROCEDURE showSalesmanLimit(x INT)
	SELECT * FROM salesman LIMIT x;

CALL showSalesmanLimit(5);
CALL showSalesmanLimit(2);
CALL showSalesmanLimit(1);
```
