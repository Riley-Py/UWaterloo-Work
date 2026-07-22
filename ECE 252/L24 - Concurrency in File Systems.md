- Files can be of random size; must be allocated to disk according to a strategy, some described below:
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