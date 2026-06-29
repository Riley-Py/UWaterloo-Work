### UNIX Pipes
- *Pipe* - set up communication between producer and consumer (see [[L06 - IPC|this for more info on producer-consumer]])
	- Producer writes one end of pipe
	- Consumer receives it on another
- Pipe creation is done like this: ``pipe (fileDescriptors[])``
	- ``fileDescriptors[0]`` is read-end
	- ``fileDescriptors[1]`` is write end
- Diagram of a pipe: 
	- ![[Pasted image 20260629101245.png]]
- Pipe is block of main memory 