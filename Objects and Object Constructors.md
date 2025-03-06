---
tags:
  - braindump
  - javascript
  - "#template"
  - odin_project
created: 2025-03-05T21:29:00
---
# Objects as a Design Pattern

```javascript
function Book(title, author, pages, read) {
  this.title = title;
  this.author = author;
  this.pages = pages;
  this.read = read;
  this.info = function () {
    return `${this.title} by ${this.author}, ${this.pages} pages, ${this.read}`;
  };
}

let book1 = new Book("Star Wars", "Brandon", 500, "not read");
console.log(book1.info());

//ES6 format
const Book = (title,author,pages,read) =>{
	this.title = title;
	this.author = author;
	this.pages = pages;
	this.read = read;
	this.info = function () {
	    return `${this.title} by ${this.author}, ${this.pages} pages, ${this.read}`;
  };
}
```