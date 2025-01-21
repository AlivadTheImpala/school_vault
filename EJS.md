#javascript #braindump 
# What is EJS
EJS is a way to create templates for the structure of your HTML, rather than creating the structure for every page manually. 

The closest thing I have that relates to this is using includes files with php. As in php, in ejs you can create your header and footer, that can be used across many different pages simply by specifying it in your page. 

# Routing
For this project I am using EJS as my templating engine. 

res.render("template", {data being provided to the page})
```javascript
import express from "express";
import { getAll } from "./data.js";
import { getItem } from "./data.js";
//render home page

app.get("/", (req, res) => {
res.render("index", {albums: getAll()} );

});
```
essentially what is happening:
we send a get request using "/" which is basically an empty url query aka the home or index page. "/" is also referred to as a virtual url. When our browser recieves a request containing "/" it renders "index"