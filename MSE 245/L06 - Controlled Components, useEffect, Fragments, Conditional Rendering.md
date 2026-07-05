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