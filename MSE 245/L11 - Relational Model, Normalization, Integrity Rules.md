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

#### Functional Dependency
- One value of primary key, at any given moment, there can only be one value for each other attribute in table
	- If attribute not functionally dependent on key, it should be in another table
- Dependencies come from requirements, not from data
- Direction matters
	- Example: `Customer_No -> Customer_Name` holds, but `Customer_Name -> Customer_No` doesn't, as there can be two identical customer names

#### Choosing Primary Key
- Criteria from [[L10 - Link Entities, Recursive, Multiple Relationships|L10]] holds, plus three more
	1. *Choose smallest candidate keys* - few columns, few bytes
	2. *Prefer numeric over alphabetic* - faster/more integrity
	3. *No unique key available for entity table, not genuine entity table*

#### Three Normal Forms
- *UNF (un-normalized form)* - raw list of attributes
	- Example:
		 ![[Pasted image 20260810201955.png]]
- *1NF* - separate repeating groups
	- Example:
		- ![[Pasted image 20260810202019.png]]
- *2NF* - separate part-key dependencies
	- Example:
		- ![[Pasted image 20260810202135.png]]
- *3NF* - separate non-key dependencies
	- *Transitive dependency* - `key -> some non-key attribute -> another non-key attribute`
	- Example:
		- ![[Pasted image 20260810202400.png]]
- Each step has perquisites to proceed to the next form

#### Three Tests for 3NF
1. For each non-key attributes, is there just one possible value for a given value of key?
	- Fails: repeating group; not in 1NF
2. Do all non-key attributes depend on whole key?
	- Fails: part key dependency; not in 2NF
3. Do all non-key attributes depend directly upon key?
	- Fails: transitive key dependency; not in 3NF
- Applied to table:
	- ![[Pasted image 20260810202629.png]]
### Merging Common Entities
- To merge:
	1. Merge versions into single entity with union of attributes
	2. Reapply 3NF test
		- Note: not necessary, as it can reintroduce dependency; if that happens split again
### 3NF to ER Diagram
- Steps to draw ER diagram
	1. *Link all entities sharing a key (primary/foreign)*
	2. *Remove all redundant links*
	3. *Add cardinalities* 
	4. *Draw ER diagram*
	5. *Add optionalities and relationship names*

#mse245 
#L11 