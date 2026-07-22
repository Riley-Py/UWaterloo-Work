### Deadlock Detection
- OS is in best position to detect deadlock, but they don't do that
	- Instead, programs like database servers check whether there is deadlock and takes action to resolve it
- Relies on model of resource allocation and requests
	- If resources have only single instance, can reduce graph to *wait-for*; removes resource boxes and only focuses on the processes
	- Diagram: 
		- ![[Pasted image 20260722131529.png]]
	- Trivial with diagram to see if there is a cycle for human; computer has more work 
		- Algorithm for computer: for each node, examine possible path and see if no further path is available after node is reached; if so, examine next path; if not, cycle is detected
### General Deadlock Detection Algorithm
- $n$ processes numbered $P_1$ to $P_n$ and $m$ resources
	- Resources are represented with two vectors: $E$ (existing resource vector; total number of instances of resource) and $A$ (available resource vector; how many instances of each resource are currently available)
		- Example: if resource $i$ has two instances total and one is assigned a process, then $E_i$ is 2 and $A_i$ is 1
- Two matrices represent the system
	- $C$ - current allocation; contains data about what resources assigned to each process
		- $i$ row is how many of each resource $P_i$ has
	- $R$ - request matrix
		- $i$ row shows how many resource $P_i$ wants
	- $