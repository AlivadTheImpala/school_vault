#javascript 

[[Objects and Arrays]]

# Finding the length of a string:
```javascript
const browserType = "mozilla";
browserType.length;

//This will return 7, because the word mozilla is 7 characters long.
//useful if trying to let a user know that theyre input is over a certain length.

browserType.length-3;
//this will return 4, because using a negative number will look at the strong from the end first and count in the specified number. So in the word mozilla, we start at a (position -0) 
```

# Retrieving a certain character in a string:
To return a certain character, you would append `[]` square bracket at the end of your variable name. inside the brackets you specify the index number of the character you want to return.
```javascript
browserType[0];
//this would return m because it is in first position. 
//Note 0 is always the first number in an index.
```
To return the last character of any string we can 

# Testing if a string contains a substring
If you want to see if a string contains a substring, in this case the 'zilla' portion of the word mozilla, we can use the **includes()** method to search for it. It returns true if it exists otherwise, it returns false.
```javascript
const browserType = 'mozilla';

if (browserType.includes('zilla')) {
  console.log('Found zilla!');
} else {
  console.log('No zilla here!');
}

```

# Extracting with slice()
Using the slice() method you can extract a portion of a string. You can give it two index values slice(start, end).
- The **end** is exclusive, meaning that it will not include the substring in the stated index number, it will only extract just before the index number.
```javascript
const browserType = 'mozilla';
console.log(browserType.slice(1, 4)); // "ozi"

//the letter at index 4 is l, but again, javascript will only extract up to the point before the stated index number. In this case, i will be extracted and stop.

//If you want to extract all remaining characters from your start point, you dont have to include the end parameter
browserType.slice(2); // "zilla"

//Conversley if you want to begin you slice starting from the end of the string, you use a negative number

browserType.slice(-5); //"zilla"
```
## Extracting with substr()
You can also use substr() to exctract a portion of the string. The difference between substr() and slice() is in the second paramter. 
- slice(start,end): in slice() the end parameter just states at what index the slice will stop
- substr(start,length): in substr() however you state where you want to start the extraction, and the second parameter specifies the length of the extraction in relation to the start position
```javascript
let text = "Apple, Banana, Kiwi";  
let part = text.slice(7, 13);//Banana
//you are explicitly stating the ending index

let part = str.substr(7, 6);//Banana
//you are stating how long the cut will be, in this case 6 index characters long.


```

# Finding the Position of a substring within a string
To find the index of a substring, you would use **indexof()**
- indexof(1,2) takes two parameters:
	- 1: the substring you want to search for
	- 2: optional; this specifies where you want to start the search
```javascript
const tagline = 'MDN - Resources for developers, by developers';
console.log(tagline.indexOf('developers')); // returns 20, the index position of developers.

//to find subsequent occurrences of a substring
const firstOccurrence = tagline.indexOf('developers');
const secondOccurrence = tagline.indexOf('developers', firstOccurrence + 1);

console.log(firstOccurrence); // 20
console.log(secondOccurrence); // 35
```

# Changing case
If you want to ensure the inputted user strings all follow the same case. you can use two methods
- toLowerCase()
- toUpperCase()
```javascript
const radData = 'My NaMe Is MuD';
console.log(radData.toLowerCase());// my name is mud
console.log(radData.toUpperCase());// MY NAME IS MUD
```

# Updating part of a string w/ replace()
replace() will replace one substring inside of a string, with another substring. It will only replace the first occurence of the substring you specifiy.
- **replace(a,b)** takes two parameters 
	- a is the substring you want to replace.
	- b is what you want to replace it with.
```javascript
const browserType = 'mozilla';
const updated = browserType.replace('moz','van');

console.log(updated);      // "vanilla"
console.log(browserType);  // "mozilla"

//This doesnt replace the original string, it only returns a new string. If you wanted to update the original string:

let browserType = 'mozilla';//declare with let not const so we can change it.
browserType = browserType.replace('moz','van');//update the variable with the replace method

console.log(browserType);  // "vanilla"
```
To replace all occurences of the substring, you would use replaceAll()
```javascript
let quote = 'To be or not to be';
quote = quote.replaceAll('be','code');

console.log(quote);  // "To code or not to code"
```

### Case sensitivity w/replace()
By Default replace is case sensitive, so you would have to make sure that what youre looking for matches with the spelling in the string your looking into
```javascript
let text = "Please visit Microsoft!";  
let newText = text.replace("MICROSOFT", "W3Schools");

//this would not replace `Microsoft` because the cases are different
```
To replace with case insensitivity use a [[regular expression]] with an /i flag
```javascript
let text = "Please visit Microsoft!";
let newText = text.replace(/MICROSOFT/i, "W3Schools");

//this would work, and replace Microsoft with W3Schools.
```

---
# Sources
[String Methods Refernce Sheet](https://www.w3schools.com/jsref/jsref_obj_string.asp)
[Mozzilla Developer String Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
