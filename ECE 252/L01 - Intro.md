### Terms
- *Operating system (OS)* - software that sits between hardware and applications
	- Responsible for resource allocation
	- Enables programs to run
	- Enables the sharing and cooperation of resources
- *Systems programming* - not part of kernel; parts of system programming include: 
	- *File Manipulation* - create, delete, rename, print, manipulate files/directories
	- *Communication* - remote login capability, file transfer, download utilities, messaging
	- *Processes/Thread Management* - creating processes/threads, working with them, interacting, and cleaning them
- *Concurrency* - if program can support two or more actions in progress at the same time
	- *Parallel* - if program can have two or more actions executing simultaneously 
- Advantages of concurrency
	- Speed up program
	- Get more work done in same amount of time
### C Toolkit
- Procedural language
	- No objects/classes
	- Functions only
- *Headers* - files that contain functions
- *Implicit declaration* - header is missing, but complier can guess what you want
- *Function prototype* - serves as a heads-up for complier to expect a function in the future
- *Comments* - begins with ``` /* ``` and ends with ``` */ ``` 
	- Comments like ``` // ``` may be permitted, but it is advised to use the above
- *Structures* - grouping of variables
	- Attributes of structure can be accessed with the dot operator
- *Type Names* - instead of writing ```struct example``` all the time to reference the structure, we can instead do ```typedef``` and define a name so that the use of ```struct``` is not needed
- *Stack memory* - local to function running
	- Goes away once function returns
	- Must initialize variable and define it, or it contains garbage
- *Global variables* - variables declared outside of any function
	- Space is not infinite
	- Not best practice
- *Heap memory* - dynamically allocated by the user
	- Use ```malloc()``` and it takes 1 parameter: amount of bytes of memory you want
		- To find the size you want to allocate, use ```sizeof``` 
		- Returns pointer to memory; doesn't need to be cast
	- Must deallocate using ```free()``` to let OS know that memory can be deallocated
		- If forgotten, it can create a *memory leak*, which can lead to a crash
		- If you call ```free()``` twice, it will crash program
		- If you free memory that was allocated on stack rather than heap, it also crashes the program
- *Pointer* - stores memory address of another variable
	- Use ```&``` to find memory address of stack variable
		- Use with caution, as stack variable doesn't outlive function or loop it is allocated in
	- Use ```*```  to find the value held by the address of the pointer
- *Cast* - explicitly converts a variable from one data type to another
- *Arrow* - shorthand for assigning members in a structure if that structure was allocated on the heap
	- Instead of ```(*p1).x```, we can instead do ```p1->x```
		- Both are interchangeable
- *Arrays* - can be allocated on stack or heap
	- *Stack-allocated array* - you use square brackets to specify size (i.e. ```int array[10]```)
		- Contains garbage
	- *Heap-allocated array* - you use ```malloc()``` to specify the size (i.e. ``int* array = malloc(10 * sizeof(int)))``
		- Have to still call ``free(array)`` to prevent leaks
	- Both have to be initialize; can be done in a couple ways
		1. For loop
		2. ``memset`` if you include ``string.h``
	- No bounds checking for arrays in C
		- Must do manually
- *Strings* - character array
	- Terminates with a byte of 0 or ``NULL``
- *Function convention*:
	1. The first parameter of a function is modified
	2. Functions have integer return types
		1. If 0, everything was good
		2. If non-0, number can aid in troubleshooting
	3. ``errno.h`` defines ``errno``, which many functions call 
- *Printing* - uses ``printf()``
	- Formats a string and writes it to console
	- Uses format specifiers
		- ``%d`` = integer
		- ``%u`` = unsigned integer
		- ``%f`` = float
		- ``%lf`` = double
		- ``%c`` = character
		- ``%s`` = list of characters (``char*``)
		- ``%p`` = memory address
- *Define Directives* - used for fixed values
	- Placed on top of program
	- Used throughout the program to avoid "magic numbers"
- *Main + Arguments* - structure is like this 
	- `````c 
	  int main (int argc, char** argv) {
	  ...
	  return 0;
	  
	  }
	  `````
	- ``argc`` is count of characters provided
	- ``argv`` is a pointer to an array of ``char*`` 
	- To convert characters to integers, use ``atoi()``
- *Void pointers* - pointer with no type

#ece252 
#L01

