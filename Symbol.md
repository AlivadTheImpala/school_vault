## Javascript
If you want your variables to be unique values, even if they technically contain the same information, you would use Symbol()

```javascript
let str1 = "JavaScript is fun!"; 
let str2 = "JavaScript is fun!"; 
console.log("These two strings are the same:", str1 === str2); 

let sym1 = Symbol("JavaScript is fun!"); 
let sym2 = Symbol("JavaScript is fun!"); 
console.log("These two Symbols are the same:", sym1 === sym2);

//Output: 
//These two strings are the same: true 
//These two Symbols are the same: false
```
In the first example, javascript sees that str1 and str2 are of the same datatype (string) AND they contain the same value (JavaScript is fun!) so the statement is true.

However in the second example each symbol is unique even if technically the values inside are the same.

>[!From the Book]
>These symbol data types can be very handy as properties of objects, which we will see in _Chapter 3_, _JavaScript Multiple Values_.

