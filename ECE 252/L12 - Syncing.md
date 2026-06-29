### Synchronization
- Relationship between events
	- Can be before, during, or after
- *Serialization* - order of events
	- Event A must take place before Event B
- *Mutual exclusion* - event C and event D can't happen at the same time
	- In IPC, one process is writing to memory that another process can't be reading from at the same time
#### Serialization - Messages
- *Sequential events* - knowing the order of events that are in order
- *Concurrent events* - can't tell by looking at the program which will happen first
	- Can't guarantee order of events
	- *Heisenbug* - software bug that disappears when a programmer tries to catch it
### Shared Data + Atomic Operations
- *Atomic operation* - an operation that cannot be interrupted
- *Mutex* - short form for mutual exclusion
	- Guarantees that when both orders of events are valid, multiple threads aren't trying to update a variable at once
#### Mutual Exclusion - Flags
- *Critical section* - code that should be accessed by max of 1 thread at a time
	- Protect these through mutexes
	- Should be short
	- Can't be ran in parallel
- Problem with flags
	- If switch happens at bad time, two threads can be critical section at once
	- If array is used, then two threads can be blocked from the critical section
- Disabling interrupts doesn't work, as system can't respond to user input or other events

#### Test-and-Set
- Special machine instruction performed in single instruction cycle
	- Not interruptible
	- Atomic read and write
- Returns boolean value
	- If true, it's the current thread's turn to enter critical section
	- If false, it's not the thread's turn
- *Busy-waiting* - one thread is constantly checking the instruction
	- Wastes time and cycles
#ece252 
#L12 