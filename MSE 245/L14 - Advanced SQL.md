### CONCAT
- Combines two ore more columns
- Example: `SELECT CONCAT(cafe_name, ', ', city) as cafe_location FROM cafe;`
- Notes
	- Output column needs an alias
	- *Computed column* - column that doesn't exist in table; only for the duration of the query

### Dates
- `DATE_FORMAT` - turns date into readable string
	- `%Y / %y` - year, 4-digit/2-digit
	- `%M / %b` - month name, full/abbreviated
	- `%m` - month number, leading 0
	- `%e / %d` - day of month, no zero/leading zero
	- `%W` - weekday name
	- `%H:%i:%s` - hour, minutes, seconds (24h)

### LIMIT
- Number of records to return
- Example: `SELECT * FROM product ORDER BY price DESC LIMIT 3` - only 3 priciest items
- Two arguments - offset from first row, and then number of rows; default is 0 offset (i.e. starts from first row onwards)
- Notes
	- Meaningless without `ORDER BY`
	- Two-argument `LIMIT` is how *pagination* (splitting blocks into pages) works

### Top-N idiom
- Three parts:
	- `GROUP BY` - one row per group with its aggregate
	- `ORDER BY` - put the interesting one first
	- `LIMIT n` - keep it
- Not allowed to nest aggregate functions in SQL

### Grouping - Computed Value
- Anything that is computed can be grouped with `GROUP BY`

### Grouping - Hidden Fields
- Using columns in `SELECT` that don't appear in `GROUP BY`
- Can only use if hidden column is unique within each group

### INNER JOIN
- Only matching rows in two tables are retrieved

### OUTER JOIN
- All rows in table A are retrieved, regardless of whether table B as NULL values or not
- `LEFT` keeps every row of the table named first; `RIGHT` keeps every row of the table named second

### UNION
- Combines results of several `SELECT` statements into one result set
- Removes duplicate rows by default; use `UNION ALL` to keep them 

### Subqueries
- Query nested inside another query
- Example: `SELECT * FROM customer WHERE customer_id = (SELECT customer_id FROM orders WHERE order_id = '1');`
	- *Outer query* - `SELECT * FROM customer WHERE customer_id = ...`
	- *Inner query* - `... (SELECT customer_id FROM orders WHERE order_id = '1')`
- Inner query is executed first, then outer query
- Most subqueries can be rewritten using joins

#### Scalar
- Returns one value
- Used with calculated columns

#### Row Subqueries
- Use `IN` instead of `=` if it returns set of rows
- Use `NOT IN` for the opposite
	- NOTE: if subquery returns single NULL, it returns no rows at all
#### FROM Subqueries
- Constructs derived table
- Must be given an alias
- Can aggregate an aggregate

### Subqueries VS Joins
-