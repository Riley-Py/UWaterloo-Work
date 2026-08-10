d- Files can be of random size; must be allocated to disk according to a strategy, some described below:
	1. *Contiguous allocation* - file occupies set of contiguous (isolated) blocks on disk
		- Can be difficult to find place to put it; don't know size of file, so can't pre-allocate
	2. *Linked allocation* - linked list of blocks, where blocks can be located anywhere on disk; directory listing just has pointer to first/last blocks
		- Requires following a pointer; if wanting to go to middle of block, have to load all of the other blocks to get there
	3. *Indexed allocation* - take all pointers and put them into an index block; first block of file has bunch of pointers
		- Go to the index block to get location of the pointer of the block where data needs to be accessed
		- All pointers start as null; when new block is added, the entry is added to index block
		- Three ways of doing this
			1. *Linked Scheme* - index block is disk block; link them together, where last entry in index block is null or pointer to next index block
			2. *Multilevel Index* - variant of linked scheme with multiple levels; first level points to second level block, where it then points to actual file data
				- Example: If block is 4KB, can have 1024 4-byte pointers, so two levels allows up to 4GB of data
			3. *Combined Scheme* - combo of the above; used in UNIX
				- Keep first 15 pointers of index block in inode structure; 12 point directly to file data
				- Next three refer to indirect blocks; 13th is index block with addresses of blocks with data; 14th points to double indirect block; 15th points to triple indirect block
		- Diagram of this: 
			- ![[Pasted image 20260722091756.png]]
- *Record locking* - use `fcntl` to lock a byte range of file instead of whole file
	- Allows for more concurrency to happen
- `fcntl(file_descriptor, command, *flockptr`)
	- `file_descriptor` - obtained using `open`
	- `flockptr` - pointer to structure `flock`, which has the following parameters
		- `l_type` - `F_RDLCK` (read lock) or `F_WRLCK` (write lock) or `F_UNLCK` (unlock)
		- `l_whence` - `SEEK_SET` (where offset begins at file) or `SEEK_CUR` (current position of file) or `SEEK_END` (user-defined endpoint of file)
		- `l_start` - offset in bytes; relative to `l_whence`
		- `l_len` - length in bytes; 0 means lock to EOF
		- `l_pid` - returned with `F_GETLK`
	- `command` has three options
		- `F_GETLK` - determine if lock described by `flockptr` is blocked by other lock; if lock exists, content of `flockptr` is overwritten, and if it doesn't, `l_type` is set to `F_UNCLK`
		- `F_SETLK` - set lock as described by `flockptr`; if lock can't be acquired, return error
			- `trylock` can be used in this case
		- `F_SETLKW` - blocking version of `F_SETLK`; if region we want to lock is in use, caller is blocked
- Simplified version of command above: `lockf(file_descriptor, command, length)`
	- `command` - can be one of four options
		- `F_LOCK` - acquire exclusive lock on section of file
		- `F_TLOCK` - try to acquire exclusive lock
		- `F_ULOCK` - unlock section of file
		- `F_TEST` - check if section of file is locked; 0 if unlocked, -1 if locked
	- `length` - offset based on current position in file; if 0, locks entire file
- Do not mix `fcntl` and `lockf` together; use one or the other

### Using File As Lock
- `git` places file `index.lock` at particular directory to indicate that operation is in progress; doesn't allow two `git` clients to operate on the same repository at the same time
- Use `open (*filename, flags)`, where `flags` are
	- `O_RDONLY` - read-only
	- `O_WRONLY` - write-only
	- `O_RDWR` - read/write
	- `O_APPEND` - append info to EOF
	- `O_TRUNC` - clear all data from file
	- `O_CREAT` - create file
	- `O_EXCl` - used with `O_CREAT`, must create file; if file exists, fail
#ece252 
#L24 