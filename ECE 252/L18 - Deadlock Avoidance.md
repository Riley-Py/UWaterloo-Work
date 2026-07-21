- Don't allow cycle in resource allocation graph

### Ordering of Resources
- Impose ordering on resource requests; resources are given order and requests must follow order
- To formalize this:
	- Set of resources: $R = \{R_0, R_1, \cdots R_m\}$
	- $f(R_i)$ assigns each resource an integer value
	- Integer value compares two resources; process may only request $R_j$ if assigned $R_i$ if $f(R_j) > f(R_i)$
	- To get $R_i$ when having $R_j$, process must release resources $R_k$ where $f(R_k) \geq f(R_i)$ 
	- If the above protocols are followed, circular-wait can't happen
	- In development, enforced by coding convention/review
### Stay Safe
- Instead of ordering, process gives OS additional info about resources requested; processes need to say in advance of execution maximum resources of each type they need
- *Safe* - some scheduling order where every process runs to completion even if all of them request max resources immediately
	- Deadlock not possible
- *Safe sequence* - guarantees program correctness when multiple threads access shared resources
- *Unsafe* - opposite of safe
	- Deadlock can occur
- Example 1: Each process can run to completion; first is b, then c, then finally a
	- ![[Pasted image 20260721152312.png]]
	- The process that can consume the max resources with the amount of free resources available goes first, consumes it to max, then releases it back to memory pool
- Example 2: Same as before, but this time, a got an extra resource initially, messing up the final sequence and not allowing completion of all resources; unsafe
	- ![[Pasted image 20260721152450.png]]
### Resource-Allocation-Graph Algorithm
- OS maintains allocation graph to avoid deadlock
- Model for resource allocation graph - three edges
	- One represents requests; process wants resource
	- One represents allocation; resource currently belongs to process
	- One represents wanting a resource in the future
- Diagram of this; dashed line is wanting resource in future, and when request is made, it gets turned into a request edge
	- ![[Pasted image 20260721152838.png]]
- Assignment allowed if converting request edge to assignment edge doesn't result in cycle
- Only works if resources are known in advance; one instance of each resource

### Banker's Algorithm
- Allows for resources with multiple instances
- Diagram of this:
	- ![[Pasted image 20260721153539.png]]
- Steps for algorithm
	1. Look for row in matrix where unmet resources are less than or equal to resources in A; no such row means state is unsafe
	2. Assume that row gets all resources it needs.  Mark process as terminated 