A string is a sequence of characters, and can be declared in: 
- Double quotes ""
- Single Quotes ''
- Backticks: \`\` special template strings, called [[#Template Literals]], in which you can use variables directly.

```javascript
let singleString = 'Hi there!'; 
let doubleString = "How are you?";

//Either option works, but stay consistent!
//you also cant start with one type of quote and end with a different one otherwise an error will kick.
```


## Template Literals
When using backticks, the advantage here is that you can then call a variable inside of the string. This makes you code a bit more readable than concatinating everything with + symbols.
```javascript
let language = "JavaScript"; 
let message = `Let's learn ${language}`; 
//you place the variable in ${nameOfVariable}
console.log(message);
//Output: Let's learn Javascript
```

Template Literals respect line breaks in the source code, so you can write strings that span multiple lines:
```javascript
const output = `I like the song.
I gave it a score of 90%.`;
console.log(output);

/*
I like the song.
I gave it a score of 90%.
*/

```
To get the same effect as above using quotes instead of backticks, you need to include the line break character ```\n
```javascript
const output = "I like the song.\nI gave it a score of 90%.";
console.log(output);

/*
I like the song.
I gave it a score of 90%.
*/
```