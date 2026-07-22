- Files can be of random size; must be allocated to disk according to a strategy, some described below:
	1. *Contiguous allocation* - file occupies set of contiguous (isolated) blocks on disk
		- Can be difficult to find place to put it; don't know size of file, so can't pre-allocate
	2. *Linked allocation* - linked list of blocks, where blocks can be located anywhere on disk; directory listing just has pointer to first/last blocks
		- Requires following a pointer; if wanting to go to middle of block, have to load all of the other blocks to get there
	3. *Indexed allocation* - take all pointers and put them into an index block; first block of file has bunch of pointers
		- Go to the index block to get location of the pointer of the block where