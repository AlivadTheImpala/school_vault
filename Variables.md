#javascript 
In Javascript, there are three different ways to declare variables.
- [[var]]
- [[let]]
- [[const]]
---
__var__ is function scoped, which means that once it's been declared, it is available to use anywhere before or after the variable was declared in a function.
var is mutable, which means you can reassign or change its datatype.

__let__ is block-scoped, which means it's only available within the open/close curly brackets where it was defined. Unlike var, let is only available on the line it was assigned and below. 

__const__ is also a block-scoped variable, but it can only be assigned a value, which cannot be reassigned later. Like let, it is only available on the line it was assigned and below.

## When to use const and let
__const__ is the recommended variable to use by default. It helps you and others who review your code know the variable's value is constant and not being reassigned elsewhere in the code.

**let** is good to use inside a loop, where you might want to create a new variable with a different value.


>You can declare variables in a few different ways:

```javascript
let user = 'John'; 
let age = 25; 
let message = 'Hello';
```

```javascript
let user = 'John', 
	 age = 25, 
	 message = 'Hello';
```

```javascript
//The comma first style is also acceptable
let user = 'John' 
, age = 25 
, message = 'Hello';
```

A variable should be declared once and then called upon using its name

```javascript
//example of calling the variable by its declaration type twice.
let user = 'John';
let user = 'Brandon';
//this can lead to an error instead declare and call.

let user = 'John'; //instead declare your variable then call the name whenever you need it.
	user = 'Brandon';//Note: we are also changing the value of 'user' here.
```
