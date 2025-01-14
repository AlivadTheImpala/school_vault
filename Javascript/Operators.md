#javascript 
Operators preform actions.
***
## Arithmetic Operators
- [[Addition]]
- Subtraction
- Multiplication
- Division
- [[Exponentiation]]
- [[Modulus]]
- [[Unary operators]]

### Assignment Operators

Every arithmetic operator has an assignment operator which allows you to write shorter code

```javascript
x += 5; 
//is the same as
x = x+5;

x **= 3;
//means
x = x**3;
```

***
## Comparison Operators
Comparison operators always output a true or false boolean value.

### Equal

Equal comes into flavors when you want to compare variables.
- Equal value only: == 
	- will return true if the values are the same, even if the dataypes are different
	- "5" has the same value as 5
- Equal value AND datatype: ===
	- will return true only when the value AND the dataype are the same
	- 5 is the same as 5 both numbers with the value 5
	- "5" is the same as "5" both strings with the value 5

### Not Equal
- != not equal, with one equal sign is loosely comparing for non-equality
- !== is checking for strict non-equality (true if the comparisons have either different values or different datatypes)
Not equal is very similar to equal, except it does the opposite—it returns true when two variables are NOT equal and false when they are equal.
```javascript
let x = 5; 
let y = "5"; 
console.log(x != y);
```
***
## Logical Operators
There are three logical operators:
- and 
- or 
- not

### and
if you want to check whether x is greater than y AND y is greater than z you would use and with the && operator.

All parts of the expression must be true to log true.

```javascript
let x = 1; 
let y = 2; 
let z = 3;

console.log(x < y && y < z); //we're checking if x is less than y AND if y is less then z. this results in true

console.log(x > y && y < z);// this results in false because x is NOT greater than y so therefore the whole statement is false.
```

### or
If you dont need to ensure that All of the statements are true, but just one of them, then use or. The operator for or is || 

```javascript
console.log(x > y || y < z);
//from the variables declared in the and section. since one of these is true, the whole expression is true
```

### not
When you need to negate a booleans value you use not to make it the opposite. 
```javascript
let x = 1;
let y = 2;
console.log(!(x < y));

//Output: while x is indeed less than y, making the statement true, we are saying we DON't want an instance where that is true, so the console will log false in this case.

```

