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
- To create event, use `event_new(base, fd, what, cb, arg)` and to destroy, use `event_free(event)`
	- `base` - base that this event will be associated with
	- `fd` - file descriptor
	- `what` - specify what kind of thing we want to be notified about
		- `EV_TIMEOUT`
		- `EV_READ`
		- `EV_WRITE`
		- `EV_SIGNAL`
		- `EV_PERSIST`
		- `EV_ET` - edge-triggered (change in readiness)
		- Can be combined with `|`
	- `cb, arg` - callback function and arguments to pass
- To add event, use `event_add(ev, tv)` and to remove it, use `event_del(ev)`

### Starting Events
- Use either `event_base_dispatch(base)` or `event_base_loop(base, flags)`, where
	- `flags` - can be one of three things
		- `EVLOOP_ONCE` - wait for events to become active, then turn active events until nothing left
		- `EVLOOP_NONBLOCK` - no waiting on events; run if ready, skip if not
		- `EVLOOP_NO_EXIT_ON_EMPTY` - normal behaviour is to exit loop when no more events are pending/active; can exit via two functions
			- `event_base_loopexit(base, tv)`
			- `event_base_loopbreak(base)`
### Cleanup
- Use `libevent_global_shutdown()` to clean up the events; last function to be called

#ece252 
#L29 