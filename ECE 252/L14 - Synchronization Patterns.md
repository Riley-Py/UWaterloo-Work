- Semaphores can be used to solve various patterns

### Signalling
- A way of indicating that something has happened
- [[L13 - Semaphores|Semaphores]] pretty much

### Rendezvous
- Expansion of signalling pattern; two threads should be at same point before either of them proceed
	- One thread posts first and the other thread posts second
	- Doesn't result in deadlock, but less efficient than last solution

### Mutual Exclusion
- 