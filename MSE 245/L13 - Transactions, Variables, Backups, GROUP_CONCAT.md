### Transactions
- *Transaction* - set of related updates forming logical unit of work; all updates in transaction are performed, or none at all
	- *Rolled back* - database returns to state if one update fails
- *Transaction Boundaries* - determined by user
	- `START TRANSACTION` - begins transaction
	- `COMMIT` - completes transaction
	- `ROLLBACK` - undo all statements, even the ones that succeeded
	- In that order
	- One transaction per operation is a single action
- Without transaction, MySQL runs in autocommit mode
- Transactions don't do the following
	- DDL can't be rolled back - implicit commit
	- Transaction doesn't fix wrong decision
	- Long transactions have a cost
#### ACID
- Transaction follows acronym
- *Atomic* - transaction can't be subdivided
- *Consistent* - DB constraints before transaction must be true after
- *Isolated* - Changes to DB aren't revealed to user until transaction committed
- *Durable* - changes permanent

### Variables
- Example: `SELECT @A := (customer_id) FROM customer WHERE customer_name = 'Maya Chen'; SELECT * FROM orders WHERE customer_id = @A;`
- Syntax
	- `@name` - user-defined session variable; assign to it creates it
	- `:=` - assignment operator inside `SELECT`
	- *Session-scoped* - variable only belongs to connection; disappears when it closes
- Preferred method is a 