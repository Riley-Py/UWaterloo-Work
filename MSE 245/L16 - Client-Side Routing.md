### Single-Page Application
- Initially requested Javascript file for basic SPA has all pages of website encapsulated
- Navigating from one page to another doesn't perform a request to web server
- Diagram of this:
	- ![[Pasted image 20260811105110.png]]

### Client-Side Routing
- Takes over to render appropriate page from initially requested JavaScript file
- Diagram of this:
	- ![[Pasted image 20260811105005.png]]
- Has nothing to do with Express routes

### React Router
- Three pieces
	- `BrowserRouter` - wraps app and connects it to browser URL/history
	- `Routes` - container holding all possible routes; looks at current URL and renders one that matches
	- `Route` - one mapping: `path` renders `element`

### Project Structure
- Subdirectories under `components` correspond to purpose of each React page
- One folder per component; file within component is called `index.js` 

### How Route Gets Matched
- Notes:
	- `path="/"` is root; shown as the first thing
	- Order in file doesn't decide winner; rank is by specificity

### Navigating
- Put `useNavigate()` on the top to perform client-side navigation between pages in app; it's a *React Hook*
- 
