### Controlled Components
- *Uncontrolled component* - browser's DOM holds "real" value and React just listens
- *Controlled component* - for inputs, use the ``value`` attribute
	- Forces input to display React value over what ``<input>`` would do internally
- Loop for componets
	- ``value = {props.search}`` - React $\rightarrow$ input; state drives what's displayed
	- ``onChange={props.onSearch}`` - input 