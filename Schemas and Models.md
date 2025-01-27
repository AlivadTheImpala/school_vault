#javascript #braindump #mongoDB #mongoose

# Vomit section
URLs Needed:
/ - The Home page this will contain all the albums
/details/id - the detail page of a given album using the \_id of the album.  

### path parameters
path parameters are noted by a colon and the parameter that you are seeking :\<parameter>  
```javascript
/details/:id 
```
In this case, id is the parameter. All this is doing is saving the string character that follows details/ and saving the value into req.params.id (req.params.\<parameter_name>). The req.params object acts as a temporary variable that holds the information you need to use.

For a basic example I could convert the string value saved in req.params.id into a number that can be used to access an objects whose id (which is a number-type) matches. 

```javascript
app.get("/details/:id", (req, res) => {
	const albumId = parseInt(req.params.id); // Convert ID portion of URL to a number
	const album = getItem(albumId); // Fetch album using getItem function

	if (album) {
	res.render("details", { album }); // Pass album to details.ejs
	} else {
	res.status(404).send("Album not found");//Handle case where album is not found
	}

});
```

>[Note] this snipped assumes I have a separate module that contains an array of album objects with a method that returns a single album object based on the id given as an argument.



