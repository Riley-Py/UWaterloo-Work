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