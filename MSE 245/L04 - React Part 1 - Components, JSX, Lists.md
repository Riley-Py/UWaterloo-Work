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