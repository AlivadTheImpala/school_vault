# Basic Functions
Javascript has a bunch of function built-in that help you accomplish certain tasks or perform certain actions. prompt(), console.log(), push(), sort() are all functions that you have used before. 

Functions are groups of statements, declarations, loops that are bundled together, and calling a function will perform that bundle. 

## Invoking Functions
You can identify a function by the parenthesis at the end like so:
```javascript
nameOfFunction();//function with no arguments
functionWithArguments("hello string", 5, true); //function that takes 3 arguments
```

## Writing a function
To create your own function you begin the the `function` keyword and then your chosen name for the function
```javascript
function sayHello(){
	let you = prompt("What's your name? ");
	console.log("Hello", you + "!");
}

//to invoke this function you just type sayHello(); This will then prompt a dialog box for the user to input their name and assign their input to the 'you' variable. Then it will log 'Hello Brandon!'
```

## Naming Functions
Some considerations when naming your functions:
- use camelCase: the first word is lower case and all subsequent words begin with a capital. 
- make sure the name describes what the function is doing. Dont be afraid to have a long name if absolutely necessary
- use a verb in the name so that it is an action. `sayHi;` rather than `hiThere;`

### Practice
write a function that adds two numbers together.
```javascript
//My code
function addTwoNumbers(x,y){
	num1 = parseInt(prompt("enter your first number "));
	num2 = parseInt(prompt("enter your second number "));
	addNumbers = num1 + num2;
	console.log(addNumbers);
}
```

# Parameters and Arguments
Parameters and arguments are used to define the information that is passed into a function. 
```javascript
function tester(para1, para2){
    return para1 + " " + para2;
}
//in this example the parameters refer to the varaiales listed inside the parenthesis of the function 

const arg1 = "argument 1";
const arg2 = "argument 2";
tester(arg1, arg2);

//when we invoke the function we insert the arguments into the corresponding parameter slots.
```

### Default or Unsuitable parameters
lets take the practice function and NOT include any arguments into the function. Javascript will defualt to giving the variables a default data type of undefined. When it tries to add two undefined variables, it will return NaN (not a number). 

We could tell javascript what the default arguments should be though:
```javascript
function addTwoNumbers(x =2, y =3){
	console.log(x+y);
}
//If no arguments are given by a user, then in this case x will default to 2 and y will default to 3. The values that are used for invoking are prioritized over hardcoded arguments.
```

If you have more arguments then there are paremeters, then Javscript will just use the first few arguments and ignore the rest:
```javascript
addTwoNumbers(1,2,3,4);

//output: 3 because javascript is only reading the first two arguments here.
```

# Special Functions and Operators
There are a few special ways to write functions that make the notation a bit shorter and easier to deal with. Mainly arrow functions which send functions as parameters. The `spread` and `rest` operators also help with working in arrays much easier.

## Arrow functions 
Arrow functions are useful when you want to write an implementation on the spot and are great for simple 1 line statements. 
```javascript
//normal syntax for a function
function doingStuff(x){
	console.log(x);
}

//Same function as above, but in arrow notation. Since there is only one parameter (x) the parenthesis around it is optional.
let doingStuff = x =>console.log(x);
//you'll create a variable that will store the outcome of the function. x is the parameter and it will be plugged into the console.log function

doingStuff("Great!");
//you envoke it by calling the variable with parenthesis. Our parameter goes inside the parenthesis (in this case the string Great!) and the string Great! will be logged to the console.

//if we have to parameters then parenthesis is required
let addTwoNumbers = (x, y) => console.log(x + y);

//if there are no parameters you must also use parenthesis
let sayHi = () => console.log("hi");//output: hi

//you can also use built-in methods in conjunction with arrow functions
const arr = ["squirrel", "alpaca", "buddy"];
arr.forEach(e => console.log(e));

//this will look at each item in the array and assign it the argument e which will then be logged to the console. 
//output:
//squirrel
//alpaca
//buddy
```

>[!Note]
>Using arrow functions combined with built-in functions is very powerful. We can do something for every element in the array, without counting or writing a complicated loop. We'll see more examples of great use cases for arrow functions later on.

## Spread Operator
The spread operator, denoted by three dots`...spread`, can be used to look into an array and grab its elements. 
```javascript
let spread = ["so", "much", "fun"];
let message = ["JavaScript", "is", ...spread, "and", "very","powerful"];

//output: "Javascript" "is" "so" "much" "fun" "and" "very" "powerful".

//we call the spread variable using `...` folowed by the name of the array we want to access. 
```

This can be used to send multiple arguments to a function. 
```javascript
//We first define our function, we add two numbers.
function addTwoNumbers(x, y) {
  console.log(x + y); 
} 
//we create an array with two numbers, call the function and grab the values of arr to use as our arguments in the function.
let arr = [5, 9];
addTwoNumbers(...arr);

//You can even use multiple spread operators as orguments.
function addFourNumbers(x, y, z, a) { 
  console.log(x + y + z + a); 
} 
let arr = [5, 9];
let arr2 = [6, 7];
addFourNumbers(...arr, ...arr2);
```

## Rest Parameter
Rest parameters use the same symbol as the spread operator `...nameofarray`, but theyre used inside the parenthesis as a parameter in a function.
 ```javascript
//Remember that if we feed a function more arguments than there are parameters to receive, Javascript will take in as many as it can and ignore the rest.
function someFunction(param1, param2) {
  console.log(param1, param2);
}
someFunction("hi", "there!", "How are you?");
//output: "hi" "there!" 
//"How are you?" is ignored

//But what if you dont know how many arguments you may need? In this case you use the rest operator to capture the rest of the arguments and store them in an array. 
function someFunction(param1, ...param2) {
  console.log(param1, param2);
}
someFunction("hi", "there!", "How are you?");
//output: hi [ 'there!', 'How are you?' ]
//you can then process this array via loop
```

# Returning function values
The return function is very important because it returns the value of the function. For example if you wrote a function that adds two numbers and only logged the result, we could see the result in the console, but we wouldnt be able to use that result elsewhere in our code.
```javascript
function addTwoNumbers(x, y) {
  console.log(x + y); 
} 
//although WE can see the result of this function when we give it two numbers, were not actually storing the result here and thus wont have access to it later.

let result = addTwoNumbers(4, 5);
console.log(result);

//output: 
//9
//undefined

//The output here is 9 AND undefined. The 9 is based on the function `addTwoNumbers.` the function contains a console.log statement so we'll see the result of the addition of 4 & 5. When we try and log `result` however, we get undefined, because the result of that addition wasnt actually stored by javascript. 

//This is where `return` comes into play. Rewrite the function and instead of logging from within the function, well return the value so that it is assigned to our `result`
function addTwoNumbers(x, y) {
  return x + y;
}

let result = addTwoNumbers(4, 5);
console.log(result);

//Output: 
//9

//Now the function is saving the result and assigning it to the variable `result` we can then log that and display it in the console or use it in another variable elsewhere.

//Below is a great example of why return is so important. We create an empty array that were going to put values into. Next we create a loop that will iterate 10 times. We call the function within the array, since we rewrote the function to return the value, it gets assigned to the result variable. Then well push the result into the empty array we had created. Well repeat that 9 more times and once thats finished we log all the array containing all of our values.
let resultsArr = [];
for(let i = 0; i < 10; i ++){
  let result = addTwoNumbers(i, 2*i);
  resultsArr.push(result);
}
console.log(resultsArr);

//output:
//[
  // 0,  3,  6,  9, 12,
  //15, 18, 21, 24, 27
//]
```

## Returning with Arrow Functions
If we want to return a one-line arrow function we dont have to include the keyword `return`.
To rewrite our `addTwoNumber` function as an arrow function it would look like this:
```javascript
let addTwoNumbers = (x, y) => x + y;

//if we had a multiline function then we'd need the `return` keyword
let addTwoNumbers = (x, y) => {
  console.log("Adding...");
  return x + y;
}
//here we just included a log statement in the function so we need to return the result so that it can be used. 
```

# Variable scope in functions
Scope pertains to where variables can be accessed from. If a variable is *in scope* we can access it. When it is *out of scope* we cant. 

## Local variables in functions
```javascript
function testAvailability(x) {
  console.log("Available here:", x);
}
//x is accessible within the function definition and so logs whatever we feed into it. If we feed it "Hi!" x is assigned Hi! and will log.
//output: Available here: Hi!

testAvailability("Hi!");
console.log("Not available here:", x);
//when we call the function elsewhere and try to log x, we get an undefined error. Since this is just a call to the function and the argument we're feeding into the function is "Hi!", x technically doesnt exist here.
//output: ReferenceError: x is not defined
```

So the reason you see Hi! from the log within the function is because its IN the function. The console.log statement inside will display the argument. The secondary console.log statement in the second example doesnt show up because it is a console.log statement that is outside of the function, so it cant see the x that has been declared inside the function.

>[!Frame of mind]
>Think of a photographer inside of a booth. They take a picture of someone that is inside the booth and shows the person their picture. They can see it since they're inside the booth. Now lets say we have another photographer outside of the booth, they take a picture of someone, but the picture can only be viewed inside of the booth because it gets sent wirelessley to a monitor inside the booth. The outdoor photographer wont be able to see the picture, but the one inside the booth will be able to see it and have it on display.

