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
- *Turnstile* - 