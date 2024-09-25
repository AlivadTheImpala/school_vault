Variables that have not been assigned a value will be of the undefined datatype. 
```javascript
let unassigned; 
console.log(unassigned);

//output: Undefined

```
Although you can manually assign a variable the undefined datatype, it's not best practice to do so. 

For example, if you have two different variables (firstName, petName) assigned with undefined, Javascript will interpret these as being equal. In actuality what we might be saying is that these variable dont currently have a value