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