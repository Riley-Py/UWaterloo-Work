### Dining Philosophers Problem
- Involves five philosophers
	- Spend their lives thinking, but need to eat; share a table with their own chair
	- Centre of table is bowl of rice with five single chopsticks
		- Diagram:
			- ![[Pasted image 20260721143306.png]]
	- When philosopher wishes to eat, they sit down at designated chair, and attempt to pickup two chopsticks that are nearest; one left, one right
	- Philosophers don't grab chopsticks out of their colleague's hands as they are polite; whoever has both chopsticks can eat rice, and when finished, puts down chopsticks to think again
- Chopstick can equal a binary semaphore
	- When all philosophers sit down at same time, each tries to grab the left/right chopstick, but they are already taken
	- None of them can eat as they are stuck
- Above scenario is *deadlock*
- Solutions
	- Limit number of philosophers to 4, due to pigeonhole principle (one pigeonhole must have at least two pigeons if there are more pigeons than holes)
	- Some try to pick up left, and some pick up the right
### Deadlock
- *Deadlock* - permanent blocking of set of processes that either compete for system resources/communicate with each other
- Involves conflicting need for resources by two or more processes
- Occurs if everyone tries to do the same thing at the same time
- Example: traffic deadlock, when all four cars try to pass each other at once
	- ![[Pasted image 20260721144125.png]]
### Reusable and Consumable Resources
- *Reusable* - used by one process at a time; not depleted by use
	- Process can lock resource, make use of it, then release it for other processes
	- Examples: processors, memory, files, semaphores
- *Consumable* - created and destroyed upon consumption
	- Example: user input, interrupts, messages, posts
	- Less likely for deadlock to occur than reusable resources

### Conditions for Deadlock
- Four conditions to occur:
	1. *Mutual Exclusion* - resource belongs to one resource at a time
	2. *Hold-and-Wait* - process holding resources may request additional resources and be forced to wait 
	3. *No Preemption* - resource can't be taken from process that holds it; process holding resource may release it
	4. *Circular-Wait* - cycle in resource allocation graph
- First three conditions true: deadlock possible
	- Fourth condition must be fulfilled for deadlock to occur
- *Resource allocation graph* - graph that tells about state of system; represents processes/resources held by which processes
	- Diagram of graph:
		- ![[Pasted image 20260721144818.png]]
	- Diagram of graph with deadlock when cycle happens:
		- ![[Pasted image 20260721144918.png]]
	- Diagram of graph with cycle with no deadlock:
		- ![[Pasted image 20260721144939.png]]
### Dealing with Deadlock
- Four basic approaches with deadlock:
	1. *Ignore It*
	2. *Deadlock Prevention*
	3. *Deadlock Avoidance*
	4. *Deadlock Detection*

#### Option 1: Ignore It
- Pretend that deadlock can never happen
	- If it does, it's someone else's fault
- Windows does this when the "not responding" dialog box appears

#### Option 2: Deadlock Prevention
- Eliminate one of the three conditions, deadlock isn't possible; below are ways to avoid conditions
	- *Mutual Exclusion* - can't be disallowed; prevents errors like crashes/inconsistent state
		- Don't need this if threads are given a copy of the data and not sharing it
	- *Hold and Wait* - process requests a resource, it doesn't have any other resource
		- Cannot release all resources, however, and releasing only some resources reduces 