### Valgrind (Memcheck)
- Look at all memory reads, writes, and checks all memory accesses and allocations/deallocations; find problems like
	- Accessing uninitialized memory
	- Reading off end of array
	- Memory leaks (failing to free allocated memory)
	- Incorrect freeing of memory (double free calls/mismatch)
	- 