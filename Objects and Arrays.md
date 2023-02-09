#javascript 

# Arrays and their properties
Arrays are basically lists. They can also hold different data types not just one. You can hold a whole variety of information in them that you may want to store in single variable.
```javascript
let colors = ["black", "orange", "pink"];//this is an array of individual strings as noted by the quotation marks around each string.
```

```javascript
//this is an array with different datatypes for the values.
let arr = ["hi there", 5, true];
console.log(typeof arr[0]);//output: string
console.log(typeof arr[1]);//output: number
console.log(typeof arr[2]);//output: boolean

```

If you define an array as a constant, you can add a new value into the array, but you can't change the whole array
```javascript
const arr = ["hi there"];
arr[0] = "new value";
console.log(arr[0]);//output: new value
 
arr = ["nope, now you are overwriting the array"];
//output: TypeError: Assignment to constant variable.
```

## Accessing Items in an Array
When you create an array, javascript will automatically assign an index value to the items, starting with 0 for the first item. to access an index you use square brackets [] with the index number inside [0]
```javascript
cars = ["Toyota", "Renault", "Volkswagen"];
console.log(cars[0]);//output: Toyota

//Using 1 would return Renault and using 2 would return Volkswagen. If we use 3 in this case, javascript would return undefined because a value does not yet exist for that index position. 
```

## Overwriting Elements
If a value exists in a particular index and you want to replace said index value, you do so by stating the variable and the index position you want to overwrite as shown below.
```javascript
cars = ["Toyota", "Renault", "Volkswagen"];
cars[0]= "Tesla";//this will replace 
console.log(cars);//output: Tesla, Renault, Volkswagen
```

## Built-in length property
If you want to know the length, or number of values in an array, all you have to do is call the variable you want to check and append **.length** to it, like so:
```javascript
colors = ["black", "orange", "pink"]
booleans = [true, false, false, true];
emptyArray = [];

console.log("Length of colors:", colors.length);//output: 3
console.log("Length of booleans:", booleans.length);//output: 4
console.log("Length of empty array:", emptyArray.length);//output: 0
```
The length property counts the number of actual values within an array. Unlike the index positional value, which starts at 0 and moves up, the length value will always be +1 of the index value. In the "colors" variable above, the length is 3, but the index value for pink is 2.
```javascript
//To extract the last value from the colors variable.
lastElement = colors[colors.length - 1];//this gives us pink as the output
```

### Empty Values
If you were to have a variable with 3 values,(highest index here would be 2)and you wanted to insert a value at an index position 2 steps above the current highest index value, you can and javascript will still count the non-existant values. 
```javascript
numbers = [12, 24, 36];//highest index is 2 (36)
numbers[5] = 48;//we insert a value into index 5
console.log("numbers", numbers);
//output: numbers [ 12, 24, 36, <2 empty items>, 48 ]
```
You can see that index position 5 gets created, the number 48, but index values 3 and 4 also get created, although they are empty currently. Array methods will show how to properly add elements into an array, as doing it this way could lead to issues.
***
# Array Methods
Array methods are functions that can perform specific actions on an array and javascript has a bunch of built-in methods to use. [[Javascript Functions]] will be covered later.

## Adding with push()
The push() method can add an element at the end of an array:
```javascript
favoriteFruits = ["grapefruit", "orange", "lemon"];//length = 3
favoriteFruits.push("tangerine");//tangerine will be added to the end of the array, and the length is now 4

//if you wanted to save the new length of the array, you could make a new variable and then use the push() method :
let lengthOfFavoriteFruits = favoriteFruits.push("lime");
```

## Replace with splice()
Splice is similar to push(), but lets you insert elements at a certain index position. Like push(), it can add elements at a specified index position and can either replace existing elements or just simply add additional elements. This method can take multiple parameters, so let's break it down. 

**splice(a,b,x,y):**
- **a**: this is the starting point of where we want to insert an element into an array
- **b**: this will dictate how many elements to delete starting from the first parameter, a.
- **x and y**: these are the elements that we want to insert into the array
```javascript
//note: "rectangle" is at index 2 in this array.
let arrOfShapes = ["circle", "triangle", "rectangle", "pentagon"];
arrOfShapes.splice(2, 0, "square", "trapezoid");
console.log(arrOfShapes);

//output: [ 'circle', 'triangle', 'square', 'trapezoid', 'rectangle', 'pentagon' ]

//since we said we wanted to insert "square" and "trapezoid" starting at index 2, "square" will now occupy index 2, "trapezoid" will occupy index 3 and the original elements will shift over to the right. 
```
In the example above, we only inserted "square" and "trapezoid" into the array. We didnt overwrite or delete any of the original elements.

If we wanted to remove the elements "rectangle" and "pentagon," we can do so by modifying the second parameter in the splice() method
```javascript
arrOfShapes.splice(2, 2, "square", "trapezoid");
console.log(arrOfShapes);

//output: [ 'circle', 'triangle', 'square', 'trapezoid' ]
```

## Combining arrays with concat()
Let's say we wanted to take two different arrays and combine them, also known as concatenating. We do this by using the **concat()** method.
```javascript
let arr5 = [1, 2, 3];
let arr6 = [4, 5, 6];
let arr7 = arr5.concat(arr6);
console.log(arr7);

//we create a new array that will hold the values of the arrays we are concatenating (arr7). We start with the first array (arr5) and feed in the second array (arr6) into the concat() method as the parameter. 

//output: [ 1, 2, 3, 4, 5, 6 ]

//if we wanted to add some other values into this new array (arr7) we can do the following:

let arr8 = arr7.concat(7, 8, 9);
console.log(arr8);

//output: [ 1, 2, 3, 4, 5, 6, 7, 8, 9 ]
```

## Deleting elements
There are a few different ways to delete an element from an array. If you specifically want to remove the last element you would use **pop()**
```javascript
arr8.pop();

//output: [ 1, 2, 3, 4, 5, 6, 7, 8 ]
```

To delete the first element you use **shift()**
```javascript
arr8.shift();

//output: [2, 3, 4, 5, 6, 7, 8 ]
```

**splice()** as before can be used to delete specific sections of an array. 
```javascript
arr8.splice(1, 3);

//previous output: [2, 3, 4, 5, 6, 7, 8 ]
//starting from index 1 (3) and deleting up to index 3 (5)

//new output: [ 2, 6, 7, 8 ]

//if you wanted to "delete" a particular element, without affecting the index of the other values, you can use the *delete* operator and it'll turn the value to an undefined value
delete arr8[0];

//output:[ <1 empty item>, 6, 7, 8 ]

```
The delete operator could be useful if you track user input for example. If you outright deleted the elements, the user input would appear as there are fewer when in reality there may be more user inputs.

## Finding Elements
the **find()** method lets you check if a certain value is present in an array and returns 

## Sorting with sort()
If you want to sort an array you can use sort() and it'll sort numbers from smallest to largest and string A-Z

```javascript
let names = ["James", "Alicia", "Fatiha", "Maria", "Bert"];
names.sort();

//output: [ 'Alicia', 'Bert', 'Fatiha', 'James', 'Maria' ]

let ages = [18, 72, 33, 56, 40];
ages.sort();

//output: [ 18, 33, 40, 56, 72 ]
```

## Reversing the elements in an array
with **reverse()** you can reverse the order of the elements. Whether the array has been sorted or not does not matter, it just takes the array as it is and reverse the order of the elements.
```javascript
names.reverse();
//output: [ 'Maria', 'James', 'Fatiha', 'Bert', 'Alicia' ]
```
***
# Multidimensional Arrays
Arrays can contain different datatypes inside of them and this includes other arrays. These inner arrays can also contain arrays themselves. 
```javascript
let someValues1 = [1, 2, 3];
let someValues2 = [4, 5, 6];
let someValues3 = [7, 8, 9];
let arrOfArrays = [someValues1, someValues2, someValues3];
//here the last array has the other arrays as elements. This is the same as if we had written: 
let arrOfArrays2 = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];

//to extract the value of a particular number, we still look for the index, but we'll use two index positions. the first to specify which array to look for, and the second index will be for the index position of the value in that array. 

let value1 = arrOfArrays[0][1];
//here, 0 states we'll look at the array at index 0 which is "someValues1". Then in "someValues1" we are looking at the value at index 1 which happens to be 2. so value1 is being assigned the number 2.
```

# Objects in Javascript