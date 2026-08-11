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

### Aliases
-  *Table aliases*: 
	- Example: `SELECT P.product_name, C.category_name FROM product P, category C`, where `P` and `C` are the aliases
- *Column aliases*:
	- Example: `SELECT order_id, order_time AS placed_at FROM orders;`, where `placed_at` is the alias
	- Need to do this to use it in React
- Must use if wanting to join a table to itself

### Aggregate Functions
- `COUNT()` - how many rows
	- `COUNT(*)` - counts rows
	- `COUNT(column)` - counts rows where that column is not null
	- `COUNT(DISTINCT column)` - counts distinct non-null values
- `SUM()` - total
- `AVG()` - mean
- `MAX()` - largest
- `MIN()` - smallest

### GROUP BY
- Collects rows into groups and computes the aggregate within each one

### HAVING/Order of Clauses
- Filters on an aggregate, like `WHERE` for rows
- Order in MySQL to write clauses
	1. `SELECT`
	2. `FROM`
	3. `WHERE`
	4. `GROUP BY`
	5. `HAVING`
	6. `ORDER BY`
- Order of execution
	1. `FROM`
	2. `WHERE`
	3. `GROUP BY`
	4. `HAVING`
	5. `SELECT`
	6. `ORDER BY`

### Aggregating Expressions/Joining Three Tables
- Works on expressions, not just columns
- *Derived attribute* - column got by aggregation
- Steps for multi-table query:
	1. Work out what tables you need
	2. List them all in `FROM`, with aliases
	3. Write one join condition per hop, following primary/foreign key pairs
	4. Add `WHERE` filters, grouping and ordering

### INSERT
- Example: `INSERT INTO orders (order_id, customer_id, cafe_id, order_time) VALUES (13, 6, 1, '2026-06-09 8:20:00)`
- If adding record into table A with foreign key from table B, make sure that table B already has record with corresponding primary key

#### INSERT...SELECT
- Example: `INSERT INTO recent_order (order_id, customer_id, cafe_id, order_time) SELECT order_id, customer_id, cafe_id, order_time FROM orders WHERE order_time >= '2026-06-05 00:00:00`
- Inserts set of records from existing table
- Columns must line up in number, order, compatible type

### UPDATE/DELETE
- `UPDATE` - change existing rows
- `DELETE` - removing them
- Need `WHERE` clause to see where to update

### DDL: CREATE TABLE
- Example:
	- ![[Pasted image 20260811082550.png]]
- Column definitions first; primary key second; then foreign keys

### Data Types
- `INT` - whole number
- `DECIMAL(n, m)` - exact numbers; `n` for total digits, `m` after the decimal point
- `VARCHAR(length)` - variable-length string up to 65 535 bytes; declare what is needed; values of different length (names, descriptions)
- `CHAR(length)` - fixed-length string; length < 256; values of same length
- `LONGTEXT` - variable length text; up to 4294967295 characters
- `DATE` - `YYYY-MM-DD`
- `DATETIME` - `YYYY-MM-DD hh:mm:ss`

### Keys in DDL
- Three rules
	1. Define table A before table B if B has foreign key referencing A; parent before child
	2. A primary key and foreign key referencing it can have different names
	3. Tables can have 0, 1, or several foreign keys

### Indexes
- Contains entry for each value that appears in column; allows for faster search on values in column
- Four things to note
	1. MySQL automatically creates unique index on primary key
	2. Index can cover 1 or several columns
	3. Don't index column with few distinct values
	4. Indexes are expensive

### ALTER TABLE/DROP
- `ALTER TABLE` - redefines structure
- `DROP` - deletes column/database

#mse245 
#L12 
