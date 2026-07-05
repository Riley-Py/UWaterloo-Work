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
	- \``