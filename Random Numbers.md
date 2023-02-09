Math.random(); will give you a random number between 0 and 1. To get a number between 0 and 100 you can multiply the function by 100

```javascript
console.log(Math.random() * 100);
54.342353425 //output
```

If you dont want the decimal you would use Math.floor
```javascript
console.log(Math.floor(Math.random() * 100));
67 //output
```
