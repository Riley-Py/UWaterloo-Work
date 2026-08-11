- Manipulative component of [[L11 - Relational Model, Normalization, Integrity Rules|relation model]] 
- Does two jobs
	1. *DML (Data Manipulation Language)* - asking questions of data and changing it
	2. *DDL (Data Definition Language)* - creating and changing structure itself
- Few aspects of SQL:
	1. *Non-procedural* - describe what you want, not how you get it
	2. *`SELECT` skeleton* - `SELECT ... FROM ... WHERE ... GROUP BY ... HAVING ... ORDER BY ...`; run in different order than they are written
	3. *Joins* - put tables back together at query
	4. *Aggregate functions and `GROUP BY`* - collapses many rows into one summary number per group
- *MySQL* - RDBMS with integration with Node.js; fast and lightweight

### SELECT
- `SELECT {attribute} FROM {table_name} WHERE {condition}`
	- Read as: "from these tables, take rows matching conditions, and show me these columns"
- Points to remember
	- *Terminate the whole statement with semicolon*
	- *Keywords are conventionally uppercase*
	- `SELECT *` means "every column"

### Comparison Operators
- `IN` - matches any listed value
	- Example: `city IN ('Waterloo', 'Kitchener')`
- `LIKE` - pattern match; wildcards
	- Example: `product_name LIKE 'C%'` - match product names that start with "C"
- Two things to know about strings
	1. *Strings go in single quotes*
	2. *`NULL` doesn't compare* - use `IS NULL` and `IS NOT NULL`

### ORDER BY
- Rows have no order
	- Rows are sorted by first attribute, ties are broken by second attribute
- `DESC` - descending order
- `ASC` - ascending order

### Choosing Columns/DISTINCT
- Choose only rows that contain unique data
- Applies to whole row of result

### Joining Two Tables
- Forget join condition - every attribute gets paired with another attribute in a table
	- Called *Cartesian product*
- Joining n tables needs n - 1 join conditions

