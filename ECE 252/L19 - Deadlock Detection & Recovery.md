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
	- $C_{ij}$ - number of instances of resource $j$ that $P_i$ has
	- $R_{ij}$ - number of instances of resource $j$ that $P_i$ wants
	- Resource is considered either allocated or available; this relationship holds: $$ \sum_{i = 1}^n C_{ij} + A_j = E_j$$
- Algorithm steps:
	1. Search for unmarked process whose requests can be satisfied with available resources in $A$; find process $P_i$ where $R_i \leq A$ 
	2. If process found, add allocated resources of that process to available process and mark the process; $A = A + C_i$; back to step 1
	3. If no process was found in step 1, algorithm stops
- Algorithm has runtime of O(m x n^2)

#### Deadlock Detection Algorithm - Example
- 4 types of resources, 3 processes
- Diagram of initial state of system: 
	- ![[Pasted image 20260722133730.png]]
- Going through algorithm
	1. Process 1 can't run due to not having resource 4 available
	2. Process 2 can't run due to not having resource 3
	3. Process 3 can run, and it runs to completion; releases resources and now $A = [2, 2, 2, 0]$ 
	4. Process 1 can't run due to not having resource 4 available
	5. Process 2 can run, and now $A = [4, 2, 2, 1]$
	6. Process 1 can run now, and $A = [4, 2, 3, 1]$
- No deadlock if $E = A$ at the end of it all; deadlock if no process can go to completion after searching

### Assumption Algorithm
- Assume deadlock
	- If operation takes too long, deadlock occurs
	- If it doesn't, then it hasn't
- Might be false positives/negatives
- Can implement this with watchdog timer; begin timer when process starts
	- If task finishes first, cancel timer
	- If timer finishes, then deadlock is assumed, and must take action
### When to Detect Deadlock
- It depends on the situation
	- If deadlock happens a lot, checking for deadlock often makes sense
	- When CPU utilization is low; when a drop in CPU usage happens, it could be an indication that deadlock occurs

### Deadlock Recovery
- Can recover by "breaking" deadlock
- Several strategies that aren't mutually exclusive to one another to recover from deadlock

#### 1. Robbery
- Preemption, basically
- Steals resources from one process and gives it to another that needs it until deadlock is broken
- System needs to choose victim