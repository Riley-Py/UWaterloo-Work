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
### ACID
- Transaction follows acronym
- *Atomic* - transaction can't be subdivided
- *Consistent* - DB constraints before transaction must be true after
- *Isolated* - Changes to DB aren't revealed to user until transaction committed