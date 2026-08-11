- Three principles
	1. Browser never talks to MySQL directly
	2. React only ever sees clean JSON
	3. Node.js is the glue between React and MySQL
### Opening Connection/Running Query
- Example: 
	- ![[Pasted image 20260811100040.png]]
	- Three steps
		1. `createConnection` - prepare connection with `.config`
		2. `query` - sends SQL; callback runs when results arrive
		3. `end` - closes the connection gracefully
			- Waits until queries are queued on connection before closing
- Call a query with `connection.query`