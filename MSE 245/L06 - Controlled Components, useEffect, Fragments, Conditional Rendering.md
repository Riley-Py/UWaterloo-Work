### Controlled Components
- *Uncontrolled component* - browser's DOM holds "real" value and React just listens
- *Controlled component* - for inputs, use the ``value`` attribute
	- Forces input to display React value over what ``<input>`` would do internally
- Loop for components
	- ``value = {props.search}`` - React $\rightarrow$ input; state drives what's displayed
	- ``onChange={props.onSearch}`` - input $\rightarrow$ React; keystroke updates state
	- Usually as a pair

### React Rendering Cycle
1. *Initial render* - app appears first time; component function runs once
2. *User interaction* - something happens
3. *State update* - handler calls setter; React records new state
4. *Re-render* - React runs affected component function again; new state utilized
5. *DOM update* - React compares its virtual DOM with real DOM and only updates what differs on screen
- When parent re-renders, all children re-render too

### State Survives Re-renders
- In ``useState``, initial value is used only on first render
	- On every other render, React only uses current stored value

### useEffect Hook
- Runs side effects after component has rendered to screen
- Use cases:
	- Update one piece of state when several others change
	- Fetch data from server
	- Manually touch DOM
	- Set up timers/subscriptions
- Run rule once and have React run it whenever inputs change/re-renders
- Here is function: ``useEffect (function, arr)``
	- ``function`` - effect to run
	- ``arr`` - controls when it runs
- Three forms of it
	- *No array* - runs after every render
	- *Empty array* - runs once on mount
	- *Array with values* - runs on mount + whenever listed value changes
### React Fragments
- Group siblings without adding any element
- Use ``<>...</>`` to do this

### Conditional Rendering
- Use ternary operator for most things
- To render something or nothing at all, you can do this: ``{condition && expression to render if truthy}`` as short-hand