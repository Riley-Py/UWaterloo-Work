- Concurrent reading/modification of record by more than one thread
- *Writer* - modifies the data
- *Reader* - reads data without modification
- Concurrency is allowed with these attributes:
	- Any number of readers can be in critical section
	- One writer may be in critical section; no readers in this case
- File systems work like this; files can be read by many threads, but only one thread can write to it, and no readers are able to read while the thread writes
- *Light switch* - first one into the critical section turns on lights (allowing readers in) and the last one turns off the lights (allowing the writer to come in and write)
- *Starvation* - a thread never gets to run; in this problem, readers are constantly reading, so the writer thread never has the chance to perform writing the data
	- Solution: use turnstile method
### Readers Writers Syntax
- `pthread_rwlock_t` is the solution for the readers-writers problem built int
- Analogous to `pthread_mutex_t`

### Search-Insert-Delete Problem
- Extension of readers-writers problem
- Operates on linked list of data
- Three types of threads:
	1. *Searchers* - examine list; can execute concurrently with each other; resembles readers
	2. *Inserters* - add new items to end of list; one insertion at a time; like readers, but only one of them can manipulate the list at a time
	3. *Deleters* - remove items from anywhere within a list; only one deleter process can access the list; like writers
#ece252 
#L16 