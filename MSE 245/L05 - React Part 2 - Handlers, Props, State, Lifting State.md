- Use the arrow form of declaring functions in React; conventionally more correct

### Event Handlers in JSX
- HTML input field fires *change event* every time value changes
- In JSX, ``onChange`` attribute does this
	- Called an *event handler*
	- Once called, React calls function, and then hands it to *event object* (named ``event``)
		- ``event.target`` - DOM element that fired the event
		- ``event.target.value`` - current text
	- Other events work same way
- Pass function by reference (i.e. ``onChange(handleChange)``, not the result of calling it: ``onChange(handleChange())``)

### Props
- Steps to setup
	1. Put the data into component
	2. Pass it as an argument to a component
- When parent passes attributes to child, React collects them as single object as first parameter, named ``props``
- Passed down only, never up
- Shares data only

### State
- Tells React to re-render whenever an update happens to a variable
- Uses this structure: ``const [searchTerm, setSearchTerm] = React.useState('')``
	- ``searchTerm`` - current state value; first render is the initial value; subsequent renders renders latest version
	- ``setSearchTerm`` - state updater function; changes state; stores new value and tells React to re-render component
- Never assign to state variable directly
- Re-render steps (using user input from keyboard as example)
	1. User types character; input fires change event
	2. React calls ``handleChange``; passes event
	3. ``handleChange`` reads ``event.target.value``; calls ``setSearchTerm(...)``
	4. ``setSearchTerm`` records new value and flags component for re-render
	5. React re-runs ``Search`` function; ``useState`` hands back updated value as ``searchTerm`` 
	6. Returned JSX contains new value; React updates screen
### Hooks
- Special function React provides that lets function component tap into React features
- Call hooks at top level of component and not inside loops/conditions/nested functions

### Callback Handlers
- Way to communicate back up
- Parent defines function and passes it down to child as prop
	- Child calls function, sending data to where it was defined