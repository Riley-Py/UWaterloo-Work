- Don't want to use threads, or can't due to race conditions, thread stack size, or limits on max of threads
- Some programming languages (Javascript) force use of Async IO
- Problem with always polling with server
	- CPU intensive; wastes CPU time

### Select()
- Allows to monitor group of sockets, telling about state of each
	- Some could be ready for read, others for write, or if exception has occured
- Syntax for `select(nfds, *readfds, *writefds, *exceptfds, *timeout)`
	- When called, blocked until one socket becomes "ready" (data available to read, space to write, or timeout); can get interrupted by signal
	- `nfds` - value of highest number file descriptor in any three sets plus 1