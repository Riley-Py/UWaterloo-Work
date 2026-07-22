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
	- `fd_set` can have up to 1024 file descriptors; implemented as bitfield, and has four functions
		- `FD_ZERO (*set)` - clear set
		- `FD_SET(fd, *set)` - add `fd` to set
		- `FD_CLR (fd, *set)` - remove `fd` from set
		- `FD_ISSET(fd, *set)` - test if `fd` part of set
	- `readfds` - sockets reading from
	- `writefds` - sockets writing from
	- `exceptfds` - sockets in exceptional state (Out-Of-Band data on TCP socket)
	- Don't need all three; can put NULL for rest of them
- After `select` returns, can check all file descriptors in set

### Example: Chat Server
- When people join chart room, send message to server; server accepts/opens connection, adds client to chat room
	- People don't always talk; nothing to send if no talking
	- Server can use `select()` to keep open for when someone has said something
		- If socket for accepting activated, accept connection, and add new socket to list for listening
		- Can send notification to other sockets regarding new connection; that would be writing
		- If someone says something, read socket and pass message to other clients
### Ps