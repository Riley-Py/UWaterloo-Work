### Processes
- Program in execution
- Composed of three things
	1. Instructions and data of program (complied executable)
	2. Current state of program
	3. Resources needed to execute program
- Two instances of a program counts as two processes

### Process Control Block (PCB)
- Data structure containing what the OS needs to know about the program
	- Created/updated by OS for each process; can be thrown away when program has finished executing/cleaned
	- Blocks held in memory and maintained in some container by kernel
- PCB typically has:
	1. *Identifier* - unique ID with the process; simple integer that increments when new process is created/reset when system is rebooted
	2. *State* - current state of process
	3. *Priority* - how important process is compared to others
	4. *Program Counter* - place to store address of next instruction to be executed
	5. *Register Data* - place to store current values of registers (*context data*)
	6. *Memory Pointers* - pointers to code/data associated with process, and any memory that OS has allocated by request
	7. *I/O Status Info* - outstanding requests, files, I/O devices assigned to process
	8. *Accounting Info* - data about process's use of resources.  Optional, but common
- Diagram of PCB:
	- ![[Pasted image 20260624211223.png]]
- Program counter and register data are updated when needed
	- When system call/trap/process switch occurs
	- Diagram of this:
		- ![[Pasted image 20260624211351.png]]
### Circle of Life
- Upon creation of process, OS creates new PCB for process/initialize data for block
	- Sets variables to initial values
	- Sets initial program state
	- Sets instruction pointer to first instruction in ``main``
- PCB will be added to set of PCBs OS maintains
	- After program is done, OS may collect accounting info, then remove PCB of active processes
#### Process Creation
- Three events:
	1. System boot up
	2. User request to start new process
	3. One process spawns another
- Some processes are started are visible to user, and some are started in background
	- UNIX calls background processes *Daemon*
- Already-executing processes may spawn others
	- Spawning process is *parent* and the one spawned is *child*
#### Process Destruction
- Happens in four ways:
	1. *Normal exit (voluntary)* - user ends them
	2. *Error exit (voluntary)* - compile a non-existent file
	3. *Fatal Error (involuntary)* - stack overflow error or division by zero
		- Can handle errors like this
	4. *Killed by another process (involuntary)* - typically user requested when program hangs
		- However, a parent can outlive the death of child and vice-versa
### Process Family Tree
- Relationship between parent/child processes has a hierarchy
	- Process has one parent, but may have 0 or more children
	- Process and descendants form *process group*
- First process in UNIX is ``init`` and is the parent of all processes
	- A process cannot disinherit a child
- When process terminates, it gives return code
- When child process finishes execution and until parent process collects the value, the child becomes *zombie*
	- Process dead but not gone
	- Still in the PCB list
	- Holds onto resources until return value is collected
- When parent dies before child does, child becomes an *orphan*
	- In UNIX, orphans are adopted by ``init``
### Five-State Model
- Five states of a process are: 
	1. *Running* - actively executing
	2. *Ready* - Not running, but ready to run if selected by scheduler
	3. *Blocked* - Not running, and not able to run until some event happens
	4. *New* - Just created, but not yet added to list of processes ready to run; on disk but not in memory 
	5. *Terminated* - finished, but not yet cleaned up (reaped)
	6. *Dispatch* - Process that is not currently running begins executing and moves into Running state
	7. *Exit* - running program finishes and return value is available
	8. *Reap* - terminated program's return value is collected by ``wait`` and resources can be released
	9. *Create* - process is created
	10. *Admit* - process in New state is added to list of processes ready to start
	11. *Unblocked* - receives the resource it was waiting for; moves to Ready state
- Diagram of this: 
	- ![[Pasted image 20260624213740.png]]
### Swapping Processes to Disk
- Process may be blocked due to not being in main memory
	- Space constraints due to stack and heap allocated to running program can be large
- OS puts part of processes on disk (*swapping*) to make room for other processes
	- Very slow, so only done when absolutely necessary
- New state is needed: *swapped*
	- Only swap part of process to disk if it is blocked
- Diagram of this: 
	- ![[Pasted image 20260624214924.png]]
#ece252 
#L04 

