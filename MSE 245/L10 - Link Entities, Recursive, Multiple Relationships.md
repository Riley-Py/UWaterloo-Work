### Link Entity
- M:N implies missing link entity
- Use *link entity, junction table, associative entity, bridge table, intersection entity* to resolve this

### Two Kinds of M:N 
1. *M:N due to repeated group of attributes* - document contains repeating group; link entity is repeating group
	- Example: Sales order - stock item: paper order form with order number, customer, date, and then table of lines down page with quantity
2. *Genuine M:N* 
	- Example: Supplier - product: can have multiple suppliers of the same product, and can have many products of the same supplier

### Rules for Resolving M:N
1. Many-many link must always be resolved by creating new link entity
2. Link entity is joined to each original entity by 1:M relationship, with "many" end at link entity
3. The "one" ends of two 1:M are always mandatory
4. The "many" end has same optionality as original M:N relationship
5. Call it *A/B link*
6. Name relationships

### Key of Link Entity
- Composite of two foreign keys
- Two cases where it isn't
	1. *Pairing can legitimately repeat*
		- Example: borrower can borrow same book copy again
	2. *Third dimension* 
		- Example: student may take same course twice, in different terms
- If composite grows past 2 columns/pairing repeats, reach for surrogate primary key and keep composite as UNIQUE constraint if rule holds

### Recursive (Unary)
- Relationship is one between entity instances of same entity type
- Example: manager who manages multiple people

#### One-to-Many
 - An entity can have many related subordinate entities in the same table, but each subordinate can have only one entity to which it answers

#### Many-to-Many
- An entity can have many related subordinate entities in same table, and each subordinate can have number of entities to which it answers
- Example: bill of materials
- Create link entity
- Two things to take from it
	1. Two foreign keys need different column names
	2. Nothing about resolution is special

#### One-to-One
- Rarest of three

### Multiple Relationships Between Same Two Entities
- Two or more different relationships may exist between same two entities
- Consequences
	1. Two relationships means two foreign key columns
	2. Can have different optionality
	3. Rule 6 applies hard

#mse245 
#L10 