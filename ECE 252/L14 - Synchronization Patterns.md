- Semaphores can be used to solve various patterns

### Signalling
- A way of indicating that something has happened
- [[L13 - Semaphores|Semaphores]] pretty much

### Rendezvous
- Expansion of signalling pattern; two threads should be at same point before either of them proceed
	- One thread posts first and the other thread posts second
	- Doesn't result in deadlock, but less efficient than last solution

### Mutual Exclusion
- *Symmetric* - two threads doing the same thing
- *Asymmetric* - two threads doing different things
- The thread that locks critical section is the only one that can unlock it for the next thread

### Multiplex
- Like mutual exclusion, but allows multiple threads in the critical section

### Barrier
- Generalization of rendezvous pattern; way of having more than two threads meet at the same point before any can proceed
- *Turnstile* - A wait semaphore, followed up immediately by a post semaphore; allows only one person to go at a time
- Barrier can never be closed again; `count` can only be incremented

### Reusable Barrier
- Fix to barrier problem of never being closed; decrements `count` after rendezvous has taken place
- Use two turnstiles; all threads wait at first turnstile until last gets there, then all threads wait at second turnstile until the last gets there and lets them all through again
	- Diagram of this:
			![[Pasted image 20260720201602.png]]
	- Steps:
		1. Threads arrive at rendezvous
		2. nth thread arrives at rendezvous
		3. Last thread unlocks fi