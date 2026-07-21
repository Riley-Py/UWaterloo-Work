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
	- Fourth condition