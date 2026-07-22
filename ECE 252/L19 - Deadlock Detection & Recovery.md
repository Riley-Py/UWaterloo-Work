### Deadlock Detection
- OS is in best position to detect deadlock, but they don't do that
	- Instead, programs like database servers check whether there is deadlock and takes action to resolve it
- Relies on model of resource allocation and requests
	- If resources have only single instance, can reduce graph to *wait-for*; removes resource boxes and only focuses on the processes
	- Diagram: 
		- ![[Pasted image 20260722131529.png]]
	- Trivial with diagram to see if there is a cycle for human; computer has more work 
		- Algorithm for computer: for each node, examine possible path and see if no further path is available; if so, examine next path; if n