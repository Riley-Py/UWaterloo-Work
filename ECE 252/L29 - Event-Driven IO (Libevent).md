- Meant for high performance applications/scalable network servers
- When something happens, take action
- Use `evthread_use_pthreads()` to configure it' return 0 on success and -1 on failure
- Each event is associated with `event_base` structure; container for set of events
	- Locking enabled - can use in multiple threads, but the loop can be used in one thread
	- Creation is done with `event_base_new()`
	- Deallocation is done with `event_base_free(base)`

### Event Notification
- *Event* - happens on file descriptor; has following lifecycle
	- *Initialized* - associated with event base
	- *Pending* - waiting for event to happen
		- If it happens, user-defined callback runs
	- *Non-Pending* - not wanting to wait for event anymore; can be re-added
- To create event, use `event_new(base, fd, what, cb)` and to destroy, use `event_fr`