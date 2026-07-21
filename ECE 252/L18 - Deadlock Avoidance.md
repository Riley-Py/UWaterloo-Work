- Don't allow cycle in resource allocation graph

### Ordering of Resources
- Impose ordering on resource requests; resources are given order and requests must follow order
- To formalize this:
	- Set of resources: $R = \{R_0, R_1, \cdots R_m\}$
	- $f(R_i)$ assigns each resource an integer value
	- Integer value compares two resources; process may only request $R_j$ if assigned $R_i$ if $f(R_j) > f(R_i)$
	- 