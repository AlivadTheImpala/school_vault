#javascript #braindump #mongoDB #mongoose

## Vomit section
URLs Needed:
/ - The Home page this will contain all the albums
/details/id - the detail page of a given album using the \_id of the album.  

path parameters are noted by a colon and the parameter that you are seeking :\<parameter>  
```javascript
/details/:id 
```
In this case, id is the parameter. All this is doing is saving the string character that follows details/ and saving the value into req.params.id (req.params.\<parameter_name>). The req.params object acts as a temporary variable that holds the information you need to use  



