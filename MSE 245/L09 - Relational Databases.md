- Databases give 4 things that array can't
	1. *Persistence* - data survives server restart/deploy/crash
	2. *Querying* - efficient evaluation
	3. *Structure and integrity* - database can refuse to store something whose category doesn't exist
	4. *Concurrency* - many users reading and writing at once
- *Relational Database* - stores data in tables
	- *Attributes* - columns in table
	- *Entity instances* - rows in tables
	- *One table = One entity* 
	- *Primary Key* - attribute that identifies each instance
- Different tables can be related to each other via key values

### Javascript Array VS. Table
1. Objects can have different keys, while in table, every row = every column
2. Values can be any type, while in table, every column has declared type
3. Order matters, while in table, no order
4. Identity is position, while in table, it's primary key
5. Value can be another array, while in table, cell has one atomic value
6. Nothing stops storing category that doesn't exist, while in table, foreign key constraint rejects category that doesn't exist

### Entities
- Want to keep data about; gets its own table
- Two tests:
	1. *Entity must have multiple instances* - if only one, not an entity
	2. *Entity must have multiple attributes* - if only one, not an entity
- Entities can be physical, events, or relationships
- Written in singular, as entity describes one row

### Attributes
- Pieces of info you keep about entity
- Four distinctions:
	1. *Permanent VS time-varying* - time-varying attributes cause trouble, as storing only current value silently destroys history; bad primary key
	2. *Required VS optional* - NOT NULL (required) VS nullable (optional)
	3. *Single-valued VS multi-valued* -very multivalued attribute is a relationship to another entity in disguise
	4. *Stored VS Derived* - derived is calculated from another; store the inputs, derive the outputs
- *Atomic* - one indivisible piece of information

### Primary Key
- Also known as *identifier*
- 