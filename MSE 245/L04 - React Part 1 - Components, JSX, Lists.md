### Components
- Functions in React 
- Returns markup
- Exported; is made available to rest of app
- Starts with capital letter
- Renders when React runs function and puts markup on screen
	- First time is *initial render*
	- When data changes, it *re-renders*
- Everything in body runs every time the component renders
- If a value doesn't depend on anything inside the component, declare it outside; otherwise, define it inside

### JSX
- Short for *JavaScript XML*
- Javascript expression that describes UI
- Can mix with actual JavaScript
- Curly braces mean "evaluate Javascript and render it"
- Differences from HTML
	- HTML attributes are written in *camelCase* in JSX
	- Tags with no children must be *self-closing* (example: ``<input .../>``)
### Lists
- Each item of a list has a unique ID that is stable
- Each item needs a *key*; special attribute that gives Reach a stable identity for each element
	- React uses this to keep track of DOM elements; which to keep/change/trow away
	- Do not use array index; it's positional and dependent on the list itself
### Numerous Components
- Split one component into several components for different jobs
- *Extracting component* - taking chunk of JSX and moving it to own function; benefits are:
	- *Readability* 
	- *Single responsibility*
	- *Reusability*
### Component Tree
- Diagram of this: 
	- ![[Pasted image 20260705141725.png]]
- *Parent/child* - ``App`` is parent of ``Search`` and ``List``; they are children
- *Siblings* - shares a parent
- *Root component* - topmost one
- *Leaf component* - doesn't render any other components
- Every component can have 0, 1, or many children

### DOM and Virtual DOM
- *DOM (Document Object Model)* - browser loads page, it builds in-memory representation as tree of objects
	- Diagram of this: 
		- ![[Pasted image 20260705141930.png]]
	- Javascript can read and change this
	- Slow to change this
- *Virtual DOM* - React creates copy of real DOM
	- React builds fresh new virtual DOM based off previous snapshot (*reconciliation*) and works out smallest set of real-DOM changes needed
	- Faster than modifying DOM directly
### Attaching React to Page
- Use ``ReactDOM.render (component, DOM_node)``
	- ``component`` - instance of component 
	- ``DOM_node`` - DOM node React should take over to create virtual DOM; usually ``root`` 
#mse245 
#L04 