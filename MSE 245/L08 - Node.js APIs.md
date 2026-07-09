- *API (Application Programming Interface)* - bridge between React front-end and back-end server
	- Front-end sends requests
	- API receives them; does work with database querying; sends responses back
### Three-Tier Architecture
- *Front-End (React)* - renders UI, captures user actions, talks to back end with *HTTP*
- *Back-End (Node + Express)* - receives HTTP requests, runs logic, talks to database, sends HTTP responses; where API lives
- *Database (MySQL)* - stores data permanently; back-end talks to it with *SQL*
### HTTP
- Stands for *HyperText Transfer Protocol*
- Every interaction is request from client and response from server
- Two parts that matter:
	1. *URL* - which resource that needs detail
	2. *Method* - what to do with said resource
- Carries data in *JSON*, plus various *status codes*
	- ``200`` - OK
	- ``201`` - Created
	- ``400`` - Bad Request
	- ``404`` - Not Found
	- ``500`` - Internal Server Error
### GET vs POST
- *GET* - request for information
	- Asks for data; no changes
	- Parameters live in URL
	- Bookmarked and shared
	- Poor for large/sensitive input
- *POST* - request that sends data to server to create something
	- Carries data in request body, not URL
	- Create or submit things
	- Keeps data out of URL
- Use *GET* to read, and *POST* to create
	- Reading never changes server's state, while creating does

### Express.js
- Gives 3 things to run web server
	1. *Routing* - decide what code runs for each URL + method combo
	2. *Middleware* - functions that process a request before it reaches your route
		- Example: parsing body, checking auth, logging
	3. *Response handling* - send data back in right format
- Example: ``app.get('/menu', handler)`` 
	- Register this as a route whenever someone calls GET for ``/menu``
	- Handler receives 2 objects
		- ``req`` - incoming request
		- ``res`` - the response being built
- ``app.listen(5000, ...)`` 
	- Starts server on port 5000 and keeps it running for incoming requests
### Route Parameters
- In the URL, the route parameter is marked with a colon
	- Example: ``'/api/hello/:name'`` where ``:name`` is the placeholder for the value
	- To access it, use ``req.params.name`` 
### REST Conventions
- URL names resource, and HTTP method names action
- ``GET /api/recipes`` - read all recipes
- ``POST /api/recipes`` - create new recipe
- ``GET /api/recipes/:id`` - read one specific recipe

### Receiving Data
- Incoming data rides in request body
- In Express, you turn it on with middleware that reads incoming JSON and attaches it to ``req.body``
- Difference between ``GET`` route
	- Data comes from ``req.body`` instead of ``req.params`` or ``req.query``
	- Input stays out of URL
### POST Endpoint
- Validation guards run first for a POST endpoint
- Status codes carry meaning
- Increment ID every time you put it
### API Call With React
- For HTTP requests, use ``fetch(url)``
	- Returns a Promise that resolves to *response object*
	- Read object as JSON
- ``await`` unwraps Promise; pauses ``async`` function until response arrives, then gives you resolved value

### Submitting Form
- To let user create data, you collect data in *controlled form* and ``POST`` it
- Each part in a submission, using recipes as an example:
	- ``event.preventDefault()`` - prevents reloading the entire page when submitting; saves user data
	- Filters user input using ``split(',')`` $\rightarrow$ ``map(trim)`` $\rightarrow$ ``filter(non-empty)``, which turns input into array
	- ``fetch`` - POST needs 3 things beyond URL
		1. ``method: 'POST'``
		2. ``Content-Type: application/json`` header so server knows how to read it
		3. ``body`` - data run through ``JSON.stringify``
		4. ``response.ok`` - true for 2xx status
#mse245 
#L08 