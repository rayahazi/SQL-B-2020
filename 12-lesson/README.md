# Stored procedures:

### Syntax:
1. `BEGIN` and `END` are inner keywords for procedures. 
2. `DELIMITER` - חוסם. will define all the code inside it as one command. 
the same as `{}` in C/C++. 
it can be anything. regualr use: `//`, `$$`
```sql
func(){
}
```
```sql
DELIMITER //

CREATE PROCEDURE proc_name(parameters: optional)
	BEGIN
	-- code to execute
    END //

CALL proc_name(parameters: optional);
```
```sql
DELIMITER $$

CREATE PROCEDURE proc_name(parameters: optional)
	BEGIN
	-- code to execute
    END $$

CALL proc_name(parameters: optional);
```
## IN and OUT
<img src="IN & OUT.png"/>

> All the variables of a program are kept in the RAM memory, in  locations: `STACK` and `HEAP`. 

In and out are keywords that can be used with parameters in a procedure declaration. 


* `IN` - is the default state. with IN the variables change only inside the procedure. 
* `OUT` - allows the procedure to change directly the values of parameters. (the parameters get the address of the values). 
