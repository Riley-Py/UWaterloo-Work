### Variables
- ``const`` - declares variable that can't be reassigned
	- Can still mutate it in the case of an array
- ``let`` - variables that need to change
- ``var`` - kind of like ``let``, but with a few catches
	- Function-scoped; leaks into surrounding function
	- Allows silent redeclaration
	- Hoisted
- Always do ``const`` as default

### Types
- ``number`` - 64-bit floats; no integer
- ``string`` - there are three quote styles
	- ""
	- ''
	- \`\` 
- ``boolean`` - true or false
- ``object`` - key-value pairs
- ``array`` - ordered list; special object
- ``function`` - values that can be passed around
- ``undefined`` - no value assigned yet; default state
- ``null`` - intentionally no value; set by programmer

### Numbers
- Numbers are 64-bit IEEE 754 floating-point number
	- Therefore, doing arithmetic on floating-point numbers are approximations
	- Use decimal library for decimal arithmetic
- ``Infinity``, ``-Infinity``, and ``NaN`` are valid ``number`` values
- To convert strings to numbers, use ``parseInt(string, radix)``
	- ``string`` - type to convert
	- ``radix`` - base number; use base 10
- To check for real numbers, use ``isFinite(number)``
	- Returns true for finite numbers; false otherwise
- To check for ``NaN``, use ``isNaN(number)``
	- Returns true for ``NaN``
	- ``NaN`` isn't equal to itself
### Strings/Template Literals
- Double and single quotes are interchangeable 
- Backticks are *template literals*
	- Can embed expressions with ``${...}`` (string concatenation)
		- Example of new string concatenation: `` `I ran ${distance} km today`; ``
		- Example of old string concatenation: `` "I ran " + distance + " km today";
		- Use the new form
	- Also read multi-line strings
- Strings are immutable
	- Methods create a copy of string
#### String Methods
- ``length`` - return length; no parameters
- ``indexOf(string)`` - returns index of given string
- ``includes(string)`` - true if string is in main string
- ``slice(start, end)`` - cuts up string from the start index to the end index, not including end index
- ``split(string)`` - split the string at the given string
- ``trim()`` - gets rid of white space
- ``toUpperCase()`` - uppercases string
- ``replace(old_string, new_string)`` - replaces old string with new string; only first match
- ``replaceAll(old_string, new_string)`` - replaces old string with new string; all instances
- ``startsWith(string)`` returns true if it starts with string

### Booleans/Truthiness
- Falsy values
	1. ``false``
	2. ``0``
	3. ``""``
	4. ``null``
	5. ``undefined``
	6. ``NaN``
- Truthy values (everything else is truthy except for the above)
	1. `"0"`
	2. ``"false"``
	3. ``[]``
	4. ``{}``
	5. ``Infinity``
### Null Versus Undefined
- ``undefined`` - value not assigned yet; default state of variable declared but not initialized; Javascript does this automatically
- ``null`` - intentionally no value; value is assigned by programmer

### Checking types
- Use ``typeof (arg)`` to check the type
	- NOTE: ``typeof(null)`` is an object; this is a bug

### Equality
- ``===`` and ``!==`` should always be used
	- ``==`` performs *type coercion*; converts operands to common type before comparing
	- ``===`` compares type and value
### Objects
- Key-value pairs; like Python dictionaries
	- Keys don't need quotes
	- Can access with dot form or bracket form
		- Example: ``person.firstName`` or ``person["firstName"]``
- ``const`` on object doesn't allow you to assign a new object, but it still allows you to modify the values of said object

### Objects to JSON
- *JSON* - JavaScript Object Notation
	- Keys must be in double quotes
- To convert from object to JSON, use ``JSON.stringify(object)``
- To convert from JSON to object, use ``JSON.parse(json)``
### Arrays
- Same as Python lists
- Can hold mixed values
- NOTE: ``typeof`` won't tell you if it's an array, so you must use ``isArray(arr)``

### Iteration
- ``for`` loop
	- Getting index
	- Skipping elements
	- Break out of loop early
- ``forEach`` loop
	- Do something for each element
	- For index, use a second parameter
- ``map`` 
	- Transform every item
	- Returns new array
	- Like Python list comprehension
- ``filter``
	- Keeps matching items
	- Returns new array
- Can chain ``map`` and ``filter``, as they return array objects
- To modify arrays in place
	- ``push(arg)`` - put something at the end of array
	- ``pop()`` - remove something and return that something
	- ``splice (start_index, end_index)`` - cut the array from starting index to ending index
### Functions
- Three ways to do in Javascript
	1. ````js
	   function greet(name) {
	   return `Hello, ${name!}`;
	   }
	   
	   ````
		- Python like
		- Use for top-level named functions
	2. ````js
	   const greet = function(name) { return `Hello, ${name}!`;
	   }
	   ````
		- Function as a value
		- Use when function is data
	3. ````js
	   const greet = (name) => `Hello, ${name}!`;
	   ````
		- Modern, compact form
		- Preferred way of declaring functions
- Javascript allows extra arguments without checking; they will be ignored
- Can give functions default values to fall back on if no arguments are provided/parameters missing

### Scope
- ``let`` and ``const`` are block-scoped
	- Only lives within the curly braces
- Scope can read variables from any enclosing scope
	- Called *closure*

### Functions Equal Values
- Functions are values
- *Anonymous functions* - defined inline; single-use
