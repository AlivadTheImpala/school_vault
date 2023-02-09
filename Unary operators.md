Unary operators are also known as increment and decrement 

```javascript
x++;
//can be 
x = x + 1;

x--;
//is
x = x - 1;
//--------------
let nr1 = 4; 
nr1++; 
console.log(nr1);

let nr2 = 4; 
nr2--; 
console.log(nr2);

//Output:
//5
//3
```

## Prefix and Postfix operators

x++ is known as the postfix unary operator: postfix gets executed after sending the variable through, and then after that, the operation gets executed.

x-- is known as the prefix unary operator: prefix gets executed _before_ sending the variable through, which is often the one you will need.

```javascript
let nr = 2; 
console.log(nr++); 
console.log(nr);
//Output:
//2
//3

//the first output is still the old value of 2. When you console log nr again, you will get the new value of 3.

```

```javascript
let nr = 2; 
console.log(++nr); //prefix will execute on the number and return that new value. 
//Output: 3
```