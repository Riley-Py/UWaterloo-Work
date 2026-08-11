- Three principles
	1. Browser never talks to MySQL directly
	2. React only ever sees clean JSON
	3. Node.js is the glue between React and MySQL
### Opening Connection/Running Query
- Example: 
	- ![[Pasted image 20260811100040.png]]
	- Three steps:
		1. `createConnection` - prepare connection with `.config`
		2. `query` - sends SQL; callback runs when results arrive
		3. `end` - closes the connection gracefully
			- Waits until queries are queued on connection before closing
- Call a query with `connection.query(sql, [params], (error, results, fields) => {});`
	- `sql` - SQL statement as a string
	- `[params]` - optional values for `?` place holders
	- `error` - `null` on success; `Error` object on failure
	- `results` - `SELECT` returns array of row updates in JSON; `INSERT/DELETE` returns object with `insertID`, `affectedRows`
	- `fields` - metadata about returned column
- Asynchronous; any code that needs results must happen inside callback function
- SQL is template literal; use backticks so it can span lines/stay readable
	- Never use `${...}`, as that leads to SQL injection
- Use one query only

### Shaping SQL Rows to Client-Friendly JSON
- Example: 
	- ![[Pasted image 20260811100757.png]]
### Placeholders
- Use `?` placeholders and pass values as an array
- Notes:
	- One `?` per value in order
	- No quotes around `?`
	- Wildcards go in Javascript, not SQL
	- Can't parameterize table/column names
### Writing Data
- Example: 
	- ![[Pasted image 20260811101107.png]]
- Notes:
	- `insertID` - the `AUTO_INCREMENT` id MySQL created
	- `afffectedRows` - how many rows the statement changed

### Connection Management
- Always call `connection.end()` or a *connection leak* can occur
- Watch error paths
- One connection runs one query at a time; queries are queued up in order

#### Pools
- Keeps set of open connections and lends one out per query
- Can cap concurrent connections
- `pool.query()` acquires, runs, and releases automatically; no need for `end()`
- Standard choice in industry
- Notes:
	- Don't create pool inside route handler
	- Don't call `pool.end()` per request; shuts down whole pool

### Error Handling/HTTP Status Codes
- *400 Bad Request* - missing input from client
- *404 Not Found* - requested record does not exist
- *500 Internal Server Error* - Query failed
- *201 Created* - write succeeded, new resource created
- To handle errors:
	1. Log technical detail on server; send client generic message
	2. Validate on server even if React form validates

### mysql2
- async/await style comes back
- Example: 
	- ![[Pasted image 20260811101949.png]]
#mse245 
#L15 