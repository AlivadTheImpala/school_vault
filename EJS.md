#javascript #braindump 
# What is EJS
EJS is a way to create templates for the structure of your HTML, rather than creating the structure for every page manually. 

The closest thing I have that relates to this is using includes files with php. As in php, in ejs you can create your header and footer, that can be used across many different pages simply by specifying it in your page. 

# Routing
For this project I am using EJS as my templating engine. 

res.render("template", {data being provided to the page})
```javascript
//server.js
import express from "express";
import { getAll } from "./data.js";
import { getItem } from "./data.js";
//render home page

app.get("/", (req, res) => {
res.render("index", {albums: getAll()} );

});
```
essentially what is happening:
I send a get request using "/" which is basically an empty url query aka the home or index page. "/" is also referred to as a virtual url. 

When our browser recieves a request containing "/" it renders "index" which is an ejs template stored in the views folder.  The second parameter that I give render is the getAll() method that is imported from my data.js module. 

Basically because of the getAll() method, I am providing the data that getAll() retrieves to index.ejs. 

Now the index.ejs template has access to the albums array through the getAll() method. 

```javascript
//index.ejs
<ul>
	<% albums.forEach((album) => { %>
	<li class="ui segment">
		<a href="/details/<%= album.id%>"><%= album.albumTitle %> by <%= album.artist %></a>
	</li>

<% }); %>

</ul>
```
now that index has access to the albums array, I use some javascript in the template to run a forEach loop that will create a List Item for each album in the array. I want to be able to click on the album to see details so an a tag is created. 

href will lead to the album by accessing the id of the album.

```javascript
//render details page
app.get("/details/:id", (req, res) => {
  const albumId = parseInt(req.params.id); // Convert ID from URL to a number
  const album = getItem(albumId); // Fetch album using getItem function

  if (album) {
    res.render("details", { album }); // Pass album to details.ejs
  } else {
    res.status(404).send("Album not found"); // Handle case where album is not found
  }
});
```
This second route has a virtual address for details and placeholder for the id. 

using req.params lets us take parameters from the URL string, because the forEach loop from index appends the album ID, the ID will be whichever album was clicked, but the entire URL will be a string. so req.params.id is wrapped in the parseInt method to convert this parameter into a number.

Now that I have the id saved in albumID I can use that as the argument for the getItem(id) method.
```javascript
const getItem = (id) => {
  return albums.find(album => album.id === id);
 
};
```