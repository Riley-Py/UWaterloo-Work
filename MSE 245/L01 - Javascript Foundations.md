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
- 