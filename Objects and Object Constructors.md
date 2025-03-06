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
function Book(title, author, pages, read){
	this.title = title;
	this.author = author;
	this.pages = pages;
	this.read = read;
	this.info = function(){
		return (`${this.title} by ${this.author}, ${this.pages} pages, ${this.read}`)
	}
}
```