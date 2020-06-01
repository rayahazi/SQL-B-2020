# UNION

#### The UNION command can combine two SELECT statements into one result.

1. each SELECT statement must have the same amount of resulted columns.
2. each column in both SELECT statements, must have the same data type.

**SYNTAX**

```sql
SELECT columns FROM table1
UNION
SELECT columns FROM table2;
```

## UNION ALL

#### UNION ALL is the same as UNION, but shows also the duplicated data. 
**SYNTAX**

```sql
SELECT columns FROM table1
UNION ALL
SELECT columns FROM table2;
```
