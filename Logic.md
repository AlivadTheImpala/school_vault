#javascript 

Logic allows our code to be more than static blocks. Depending on the outcomes of certain expressions, we can create paths for our code to follow. 

 **Types of Logic statements:**
- if and else statements
- else if 
- conditional ternary operators
- switch statements
***

## if and if else statements
With an if  and if else statement, the template we are asking for is
> if a certain condition exists, then a specific action will take place. Else some other action will take place

For example, _if_ it is raining then, I will take my umbrella, _else_ I will leave my umbrella at home. It is not that much different in code:

```javascript
let rain = true; //here we state that it is raining
if(rain){ //the if states what happens when its raining
  console.log("** Taking my umbrella when I need to go outside **");
} else { //the else states what happens when its not raining.
  console.log("** I can leave my umbrella at home **");
}
//Because rain is set to true then we follow the first if statement
//Output: ** Taking my umbrella when I need to go outside **
```

The syntax of the if statement includes parenthesis if(). Whatever is in the parenthesis is translated to a boolean value. If the boolean value is true it executes the code associated within the if statement marked by the {} braces.

The else block is associated with a false boolean value. 

>[!Common mistake with if]
>```javascript
>>let hobby = "dancing";
if(hobby = "coding"){
  console.log("** I love coding too! **");
} else {
  console.log("** Can you teach me that? **");
}
//Output: ** I love coding too! **
//expected: Can you teach me that?

Inside the if statement above, the equal sign reassigns the hobby variable with coding. The context is that we only want to execute the if statement if hobby was declared as "coding" otherwise, execute the else. Since hobby was set to "dancing", we expect the else statement to execute, but since we accidentally reassigned hobby inside the if statement, that technically makes the statement true, leading to the if statement executing.

## else if statements

an else if statement is just an if statement 
- "if certain conditions exist execute code" 
	- else if "something different from the first condition exists, execute this code" 
		- else if "another condition, separate from the first two exists, execute this other code"
			- else "if none of the previous conditions exist or apply, then execute this final code."

The *else* ends the *if*

```javascript
//we declare the variables
let age = 10;
let cost = 0;
let message;

//if the age is less then 3, ticket is free, and show the message.
if (age < 3) { 
    cost = 0;
    message = "Access is free under three.";
    
  // if the ages is between 3 and less then 12, ticket is $5, show message.  
} else if (age >= 3 && age < 12) {
    cost = 5;
    message ="With the child discount, the fee is 5 dollars";
    
  //if age is between 12 and less then 65, ticket is $10, show message.  
} else if (age >= 12 && age < 65) {
    cost = 10;
    message ="A regular ticket costs 10 dollars.";
    
  //for those above 65, the cost is $7. it is implied here because we've already set conditions for all ages less than 65 in the previous else if statements.
} else {
    cost = 7;
    message ="A ticket is 7 dollars.";
}
console.log(message);
console.log("Your Total cost "+cost);
```

>[!Note]
>The code here is read by the interpreter from top to bottom. As soon as a true value is encountered, all the other ones will be ignored. <br> 
>Because of these you could write the code above like so:
>```javascript
>if(age < 3){
  console.log("Access is free under three.");
} else if(age < 12) {
  console.log("With the child discount, the fee is 5 dollars");
} else if(age < 65) {
  console.log("A regular ticket costs 10 dollars.");
} else if(age >= 65) {
  console.log("A ticket is 7 dollars.");
}
>

## Conditional Ternary Operators

Ternary operators have three operands.
```javascript
operand1 ? operand2 : operand3;
//-----------------------------------
//you can read the ? as "then" and the colon as "else"
expression ? statement for true : statement associated with false;

//if operand1, then operand2 : else operand3
```
- operand1 is the expression to be evaluated
- operand2 is executed if the expression is true
- operand3 gets executed if the expression is false
```javascript
let access = age < 18 ? "denied" : "allowed";
//here we are declaring a variable that states if the age is less than 18 then access is denied, else access is allowed.

//you can also specify an action in a ternary statement:
age < 18 ? console.log("denied") : console.log("allowed");

```

Ternary operators are good to use for short actions like in the example, but if your logic contains multiple comparisons, then an if-else statement should be used.

## Switch Statements

>[!Syntax of Switches]

```javascript
switch(activity) {
  case "Get up":
    console.log("It is 6:30AM");
    break;
  case "Breakfast":
    console.log("It is 7:00AM");
    break;
  case "Drive to work":
    console.log("It is 8:00AM");
    break;
  case "Lunch":
    console.log("It is 12:00PM");
    break;  
  case "Drive home":
    console.log("It is 5:00PM");
    break;    
  case "Dinner":
    console.log("It is 6:30PM");
    break;
}

//the expression will go inside the switch. The expressions value will correspond with the case and execute that code. 

//You add a break statement to end the switch once the matching code has ran, otherwise the switch will cycle all of the cases where the expressions value was matched, to the end of the switch statement.
```

### Default Case
Like the else, in an if-else statement, the default case is the code that will be executed if no other case matches.
```javascript
switch(expression) {
  case value1:
    // code to be executed
    break;
  case value2:
    // code to be executed
    break;
  case value-n:
    // code to be executed
    break;
  default:
    // code to be executed when no cases match
    break;
}
```
>[!Note]
>Although the default can be placed first or in the middle of a switch, the convention and expected standard is to place it at the end, in the same vain as an ending else

### Combining Cases
If you want certain cases to provide the same outcome all you would need to do is place the cases on top of each other like so:

```javascript
switch(grade){
// D and F are both failing grades :(
  case "F":
  case "D":
    console.log("You've failed!"); 
    break;
  case "C":
  case "B":
    console.log("You've passed!");
    break;
  case "A":
    console.log("Nice!");
    break;
  default:
    console.log("I don't know this grade.");
}
```
You COULD write this exact code, but in an if-else statement and it would look like this:
```javascript
if(grade === "F" || grade === "D") {
  console.log("You've failed!");
} else if(grade === "C" || grade === "B") {
  console.log("You've passed!");
} else if(grade === "A") {
  console.log("Nice!");
} else {
  console.log("I don't know this grade.");
}
```
It's not THAT bad, but the switch makes it easier to read quickly.


