### Separate Python Service for AI
- Machine learning lives in Python - libraries are only available in Python
- Split by responsibility - Node/Express handles API + SQL; Python handles model
- Each part is written in language best suited to its job - microservices
- Two services talk over HTTP + JSON
- Node's concurrency comes from single-threaded event loop; keeps Node lean

### Architecture
- Diagram: 
	- ![[Pasted image 20260811102950.png]]
- Notes:
	- Same frontend, two services - recipes comes from Node/SQL, while predictions come from Flask
		- *Gateway route* - node calls flask
### Flask
- Like Express for Python
- *Route* - decorated function instead of a callback; return value is response instead of `res`
- Diagram:
	- 
	- ![[Pasted image 20260811103221.png]]
### Training VS Inference
- Diagram:
	- ![[Pasted image 20260811103408.png]]
- Separating keeps web service fast
- *Inference* - load frozen model, make predictions
- Matters due to factors like:
	- Training is slow; inference must be fast
	- Training is not repeatable per request
	- Serving path has no dataset

### CORS
- *Cross-Origin Resource Sharing* - declaring which other origins may read its response; browser rule only
	- *Origin* - scheme + host + port; all must match