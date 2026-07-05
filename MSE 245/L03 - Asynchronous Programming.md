### Blocking
- Opening file or sending request stops program and waits for operation to finish
- In Node.js, it uses one thread plus an event loop
	- Hands off work to OS, and then moves on to other code while waiting for request to be fulfilled
- ``setTimeout`` is a callback function
	- Registers timer with OS
	- Allows for other operations to happen while waiting for an operation
	- Fake async operation
### Event Loop
- Three pieces
	1. *Call stack* - where Javascript code lives; one thing runs at a time
	2. *Node internals/OS* - slow operations happen in parallel off main thread
	3. *Callback queue* - a first-in-first-out queue of completed callbacks
- Rule: when call stack is empty, pull one callback off queue and run it
- Synchronous code always run to completion first
- To read files, you have to express dependency between two operations explicitly
	- Put the dependent call inside the callback of call it depends on
	- Creates *callback hell*, as there are many levels of indentation
### Callback Convention
- ``err`` and ``result`` is called as convention
	- ``err`` - null on success; ``error`` object with ``.message``, ``.code``, and stack trace on fail
	- ``result`` - operation produced; file handle, number of bytes read, rows of database query; only valid if ``err`` is null
- To handle errors, you do early return and exit the program (like C)
- Errors don't come up through async