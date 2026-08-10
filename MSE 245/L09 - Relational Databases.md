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
- Uniquely identifies individual instances of an entity type
- *Simple VS Composite key* - composite key is two or more attributes that are unique together though neither is unique alone
	- Example: pair of order/product ID; by themselves, not unique, but together, only one pair ever exists
- *Candidate* - attribute that could serve as key; ones that aren't chosen are called *alternate*
	- Example: for employee, employee number, SIN, work email are candidates, but one gets the job, and the others are alternates
- *Surrogate (artificial) key* - no meaning outside database; auto-incrementing integer to identify the row
	- *Natural key* - real-world identifier that exists
- Criteria for primary key
	1. *Not change in value*
	2. *Not be null*
	3. *Is unique*
	4. *Wary of keys that refer to locations/people that can change*
- Reliable candidate keys are ones somebody deliberately issued as identifier

### Foreign Key
- Relationships are due to matching primary-foreign key
- Primary key from another table; stored to connect related records between two tables
- Rules for foreign key
	1. *Foreign key can be null*
	2. *Table can have several foreign keys*

### Degree
- *Unary* - relationship between instances of the same entity
- *Binary* - relationship between instances of two different entities

### Cardinality
- For one instance of A, how many instances of B
- *One-to-one (1:1)* - one instance of A, one instance of B and vice versa
- *One-to-many (1:M)* - one instance of A, many instances of B, but many instances of B only match to one instance of A
- *Many-to-many (M:N)* - one instance of A, many instances of B, and vice versa

### Crow's Foot Diagram
- Diagram of this: 
	- ![[Pasted image 20260810161118.png]]
- Pick entity, travel along line, and read symbol at far end
- Example
	- ![[Pasted image 20260810161220.png]]
	- One category may contain zero, one, or more recipes
	- One recipe must belong to exactly one category

### Implementing 1:M
- Foreign key always goes on "many" side

### Implementing M:N
- Must be transformed into two 1:M relationships with third table
	- Called *link, junction, bridge, associative* entity/table

