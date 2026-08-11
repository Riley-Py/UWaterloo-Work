### Relational Modal
- Comprised of three components
	1. *Structural component - tables* - consisting of rows and columns
	2. *Manipulative component* - set of operations that act on tables and produce tables (SQL)
	3. *Rules of maintaining database integrity*
- Diagram of model to database:
	- ![[Pasted image 20260810200910.png]]
### Four Rules Applied to Tables
1. *Order of rows must not be significant* - if order is needed, store them by a column and sort them with `ORDER BY`
2. *Order of columns must not be significant* - refer to columns by name, not by position
3. *Each row must be unique* - primary key
4. *Each column must have only one value per row*

### Building Relational Model
1. *Identify attributes* - what information does business record
2. *Find appropriate entity type for each attribute*
3. *Identify relationships*
4. *Compare the result with the entity model built earlier*

### Normalization
- Examining lists of attributes and applying set of rules to convert them that minimizes duplication, avoids redundancy, and ensures data integrity