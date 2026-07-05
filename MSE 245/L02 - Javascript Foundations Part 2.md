### Ternary Operator
- Takes three operands
	- Condition
	- Value-if-true
	- Value-if-false
- General structure: ``condition ? true : false``
- Good for simple choices
- Bad for nesting

### Looping Part 2
- ``for...of`` is going through items in collection; works on arrays, strings, maps, sets, anything iterable
	- For both value and index, use ``entries()``
	- ``foreach`` and ``for...of`` do the same thing
- ``for...in`` - for objects walking through property names
	- Gives you key; to get value, must access it with the key
		- Example: ``user[key]``