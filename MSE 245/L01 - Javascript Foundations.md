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
	- ``radix`` - base 10