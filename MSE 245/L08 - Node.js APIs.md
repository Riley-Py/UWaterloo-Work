- *API (Application Programming Interface)* - bridge between React front-end and back-end server
	- Front-end sends requests
	- API receives them; does work with database querying; sends responses back
### Three-Tier Architecture
- *Front-End (React)* - renders UI, captures user actions, talks to back end with *HTTP*
- *Back-End (Node + Express)* - receives HTTP requests, runs logic, talks to database, sends HTTP responses; where API lives
- *Database (MySQL)* - stores data permanently; back-end talks to it with *SQL*
### HTTP
- Stands for *HyperText T*