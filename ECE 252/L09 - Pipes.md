### UNIX Pipes
- *Pipe* - set up communication between producer and consumer (see [[L06 - IPC|this for more info on producer-consumer]])
	- Producer writes one end of pipe
	- Consumer receives it on another
- Pipe creation is done like this: ``pipe (fileDescriptors[])``
	- ``fileDescriptors[0]`` is read-end
	- ``fileDescriptors[1]`` is write end
- Diagram of a pipe: 
	- ![[Pasted image 20260629101245.png]]
- Pipe is block of main memory as a circular queue
	- Each entry in queue is fixed in size/one character
- Sender may place message into queue in small chunks, but receiver gets data one character at a time
	- Both need to know when the message is finished; can use termination character or how many characters the message will have
- *Named pipe* - pipe stored on disk
	- Pipes traditionally only as long as processes are communicating
	- Named pipes are bidirectional (i.e. only need one pipe for send/receive)
- Pipes depend on file descriptors
	- Parent-child relationship required
- To create named pipe, use ``mkfifo`` (make first-in-first-out)
	- Can be manipulated like a [[L03 - Files|file]]
### Shared Memory
- Particular region of memory designated as being shared between multiple processes, where they can read and write to location
- Normally, regions of memory are only associated with one process, and if others try to read from section, they can't
- If process that creates shared memory is terminated, memory can be used by the 2nd process
- Diagram of this:
	- ![[Pasted image 20260629102036.png]]
- Can overwrite another's changes, but is solved with [[L13 - Semaphores|semaphores]]
- To share section of memory:
	1. Obtain a key that identifies specific memory segment (see [[IPC|this]] for more info)
	2. Create new shared memory segment utilizing ``shmget (key, size, shmflg)``
		- ``key`` - key specified, or ``IPC_PRIVATE``
		- ``size`` - amount of bytes shared memory should be
		- ``shmflg`` - access permissions
			- ``IPC_CREAT`` is used to create segment with key, and ``IPC_EXCL`` is used to make sure that the key used isn't being used elsewhere; can be combined using `|` operator
	3. Attach shared memory segment (add shared segment to process calling attach) - ``shamat (shmid, shmaddr, shmflg)``
		- ``shmid`` - ID of shared memory returned by ``s
	4. Detach from shared memory segment (if forgotten, it happens automatically) - ``shmdt``
	5. Delete shared memory segment; done only by one process - ``shmctl``