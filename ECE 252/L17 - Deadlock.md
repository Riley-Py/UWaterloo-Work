### Dining Philosophers Problem
- Involves five philosophers
	- Spend their lives thinking, but need to eat; share a table with their own chair
	- Centre of table is bowl of rice with five single chopsticks
		- Diagram:
			- ![[Pasted image 20260721143306.png]]
	- When philosopher wishes to eat, they sit down at designated chair, and attempt to pickup two chopsticks that are nearest; one left, one right
	- Philosophers don't grab chopsticks out of their colleague's hands as they are polite; whoever has both chopsticks can eat rice, and when finished, puts down chopsticks to think again
- Chopstick can equal a binary semaphore
	- When all philosophers sit down at same time, each tries to grab the left/right chopstick, but they are already 