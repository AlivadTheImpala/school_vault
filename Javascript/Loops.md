#javascript 

# While Loops

A while loop executes a block of code as long as an expression evaluates to true.
```javascript
while (condition) {
  // code that gets executed as long as the condition is true
}
```

The example below loops as loops and prints the numbers 0-10
```javascript
let i = 0;
while (i < 10) {
  console.log(i);
  i++;
}

//here we begin with the variable i and starting at 0. 
//in the while loop we set the condition that i must be lower than 0. 
//if true it logs to the console.
//then 1 is added to i and the i loop restarts until the condition is met.

//Output: 0 1 2 3 4 5 6 7 8 9 
```

Let's say we wanted to look for a specific value inside an array.

```javascript
let someArray = ["Mike", "Antal", "Marc", "Emir", "Louiza", "Jacky"];
let notFound = true;
while (notFound && someArray.length > 0) {
  if (someArray[0] === "Louiza") {
    console.log("Found her!");
    notFound = false;
  } else {
    someArray.shift();
  }
}

//we set the value of notFound as a true boolean, in the condition it is true. 

//We state "&& someArray.length > 0" because if the value just didn't exist in the array to begin with, then we'd get stuck in an infinite loop. we can remedy by removing any element that isnt the one we want.

//the shift method removes any array element that isn't in index position 0 that equals Louiza.

//The if portion of the loop, is the true, so once the conditions match the if statement, the console prints and notFound is turned into a false boolean.  
```

## Fibonacci Sequence with a While loops
In the Fibonacci sequence, every value is the sum of the two previous values, starting with 0 and 1. We create two numbers 0 and 1 and create a temporary value that holds the value of the next iterations nr2. nr1 becomes the previous nr2 and nr2 is assigned the value of temp, the sum of the previous nr1 +nr2. 

Next we add the numbers into an array and limit the array to a length of 24 elements so that we don't create an infinite loop of the Fibonacci sequence.
```javascript
let nr1 = 0;
let nr2 = 1;
let temp;
fibonacciArray = [];
while (fibonacciArray.length < 25) {
  fibonacciArray.push(nr1);
  temp = nr1 + nr2;
  nr1 = nr2;
  nr2 = temp;  
}
```

## do while loops
There are instances where you need to execute a code block at least once. This could be to check a valid input from a user. You might need to execute this code until a valid input is given, otherwise the rest of the code wont be ran.

```javascript
do{
//do this code while the condition in the while loop is true.
} while(condition);
```

The do portion of the code will run once and then check the while condition, if it's true the code will execute again until it returns a false, ie; it doesn't match the conditions that make the while condition true. 
```javascript
let number;
do {
  number = prompt("Please enter a number between 0 and 100: ");
} while (!(number >= 0 && number < 100));

//this code asks a user to enter a value between 0 and 100. If user input is not between 0 and 100 then the while loop is true and the "do" will run again. 
//Once the user enters a number that is between 0 and 100, the while loop becomes false, and the code stops executing.
```

## for loops
syntax:
```javascript 
for (initialize variable; condition; statement) { 
  // code to be executed
}
```
**What they mean**
- initialize variable:  this creates the initial variable and its value for the loop
- condition: as long as this condition is true the loop will keep iterating.
- statement: after every iteration, this statement will get executed

Example
```javascript
for (let i = 0; i < 10; i++) {
  console.log(i);
}
//the flow of this for loop
//create initial variable i, and set it to 0. 
//check if i is less than 10. It is so log i (0).
//Then execute the statement, increate i by 1, repeat.

//This only checks up  to the number 10 since 10 is not less than 10, and we didnt state "or equal to" 10, the code stops there and only logs the numbers 0-9.
```

### Adding values into in array
You could use a for loop to generate values to be inserted into an array using **[[push()]]**
```javascript
let arr = [];
for (let i = 0; i < 100; i++) {
  arr.push(i);
}
//push will add i into the empty array variable, arr. each increment will be added to the end of the array.
//this loop will log only those values that are less then 100, but not 100 itself, unles we included <=

//output
[
   0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11,
  12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23,
  24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35,
  36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47,
  48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59,
  60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71,
  72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83,
  84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95,
  96, 97, 98, 99
]

//to log only even values well increment i by 2 in the statement.
let arr = [];
for (let i = 0; i < 100; i = i + 2) {
  arr.push(i);
}

//output:
[
   0,  2,  4,  6,  8, 10, 12, 14, 16, 18, 20,
  22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42,
  44, 46, 48, 50, 52, 54, 56, 58, 60, 62, 64,
  66, 68, 70, 72, 74, 76, 78, 80, 82, 84, 86,
  88, 90, 92, 94, 96, 98
]
```
Typically you'll see `i++` as the statement in the for loop, this means i + 1. You can write any statement though depending on what you want the outcome to be.

## Nested Loop
Loops can sometimes be nested inside of another loop, although its typically not the best approach to a solution. They come in handy when you want to create an array of arrays
```javascript
let arrOfArrays = [];
for (let i = 0; i < 3; i++){
  arrOfArrays.push([]); //this creates the main arrays. we are pushing an array into arrOfArrays as long as i is less then 3
  for (let j = 0; j < 7; j++) {
    arrOfArrays[i].push(j);//this inserts the values into each array.
  }
}

//output: 3 arrays 
[
  [
    0, 1, 2, 3, 4, 5, 6
  ],
  [
    0, 1, 2, 3, 4, 5, 6
  ],
  [
    0, 1, 2, 3, 4, 5, 6
  ]
]

console.table(arrOfArrays);
┌─────────┬───┬───┬───┬───┬───┬───┬───┐
│ (index) │ 0 │ 1 │ 2 │ 3 │ 4 │ 5 │ 6 │
├─────────┼───┼───┼───┼───┼───┼───┼───┤
│    0    │ 0 │ 1 │ 2 │ 3 │ 4 │ 5 │ 6 │
│    1    │ 0 │ 1 │ 2 │ 3 │ 4 │ 5 │ 6 │
│    2    │ 0 │ 1 │ 2 │ 3 │ 4 │ 5 │ 6 │
└─────────┴───┴───┴───┴───┴───┴───┴───┘
```

## Loops and Arrays
Loops can make working with arrays a lot more comfortable. you can use the length property and use it in the condition part of a ``for`` or `while` loop.
```javascript
let names = ["Chantal", "John", "Maxime", "Bobbi", "Jair"];
for (let i = 0; i < names.length; i ++){
  console.log(names[i]);
}

//output:
//Chantal
//John
//Maxime
//Bobbi
//Jair
```
The length property determines the max value of our index, i. each time i will increase by 1 until it reaches the length.

If we wanted to change the values of the array, the values would change in the loop and and then we assign that new value to names while specifing the index i. 
```javascript
let names = ["Chantal", "John", "Maxime", "Bobbi", "Jair"];
for (let i = 0; i < names.length; i ++){
  names[i] = "hello " + names[i];
  console.log(names[i]);
}

//this would output:
[
  'hello Chantal',
  'hello John',
  'hello Maxime',
  'hello Bobbi',
  'hello Jair'
]

//in this example we are filtering for names that startwith M and deleting them. 
let names = ["Chantal", "John", "Maxime", "Bobbi", "Jair"]; 
for (let i = 0; i < names.length; i ++){ 
  if(names[i].startsWith("M")){
    delete names[i];
    continue;
  }
  names[i] = "hello " + names[i]; 
} 
console.log(names);
//output:
[
  'hello Chantal',
  'hello John',
  <1 empty item>,
  'hello Bobbi',
  'hello Jair'
]
```