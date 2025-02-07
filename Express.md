#javascript #express 

# Routing
```javascript
app.METHOD(PATH, HANDLER)
```

- `app` is an instance of `express`.
- `METHOD` is an [HTTP request method](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_methods), in lowercase.
- `PATH` is a path on the server.
- `HANDLER` is the function executed when the route is matched.

```javascript
const express = require("express");
const app = express();

//this is a route for the homepage.
app.get("/", (req, res) => {
	res.type("text/plain");
	res.send("Meadowlark Travel");
	});

//this is a route to the about page. 
app.get("/about", (req, res) => {
	res.type("text/plain");
	res.send("About Meadowlark Travel");
	});
```

app is an instance of the express class, by using it we have access to express tools. get() could be any of the valid HTTP request methods like post or delete for example. 