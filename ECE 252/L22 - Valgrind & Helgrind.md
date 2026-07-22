### Valgrind (Memcheck)
- Look at all memory reads, writes, and checks all memory accesses and allocations/deallocations; find problems like
	- Accessing uninitialized memory
	- Reading off end of array
	- Memory leaks (failing to free allocated memory)
	- Incorrect freeing of memory (double free calls/mismatch)
	- Incorrect use of C standard functions like `memcpy`
	- Using memory after it's been freed
	- Asking for invalid number of bytes in allocation
- Errors will be reported in console when they occur
- How to read leak summary:
	- *Definitely lost* - memory leak
	-  *Indirectly lost* - problem with pointer based structure; fixing lost items fixes this
	- *Possibly lost* - program leaking memory unless weird things are going on with pointers where they're pointing to middle of allocated block
	- *Still reachable* - memory still allocated might otherwise have been freed, but references still exist
	- *Suppressed* - what to ignore
### Helgrind
- Detect errors in POSIX pthreads
- Three basic categories:
	1. Misuses of pthreads
	2. Lock ordering problems
		- Builds directed graph of lock acquisitions; checks to see if cycle exists if deadlock is possible
		- Reports error for initial order
	3. Data races
#ece252 
#L22 