### Stateful Lists
- To make a list stateful, hand initial array to ``useState``
	- Allows list to be updated
- Never mutate state directly; build new value and pass it to the setter
- *Spread operator* - JavaScript that copies object's contents into new one (use ``...list``)

### Inline Handlers in JSX
- Don't need to write helper function
- Two ways of doing this:
	1. ``bind`` - makes new function with some arguments fixed in advance
		- Example: ``onRemoveItem.bind(null, item)`` is a function, when called, runs ``onRemoveItem(item)``
	2. *Wrapping arrow function* - React holds onto it and calls it on click, which points to ``onRemoveItem(item)`` 
		- Example: ``onClick= {() => onRemoveItem(item)}``
- Keep them small; one-liners only
	- Examples: adding, deleting
### Simulating Data Load
- Three changes to turn static list into "loaded" one:
	- Start state as empty array
	- Write function that returns Promise of data
	- Call it from ``useEffect`` so it runs after first render
- Component must render first, and data arrives after; calling fetch in body re-fire on every render

#mse245 
#L07 