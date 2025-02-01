#javascript 

Javascript is a weakly typed language which means the amount or types of datatypes aren't as robust as in other languages like C.

7 primitive datatypes
- [[String]]
- [[Number]]
- [[BigInt]]
- [[Boolean]]
- [[Symbol]]
- [[Undefined]]
- [[Null]]


### Checking Type
typeof operator - returns a string f the datatype primitive 
instanceof operator - Returns a Boolean if a value matches the datatype

0 and ' ' (empty string) are both falsey values? 0 in relation to numbers and ' ' in relation to strings. 

> [!note]
> Falsey Values are values that equate to something being false, empty, zero, or undefined 
> The number zero 0 and an empty string ; usually refer to something being false or undefined.



if we set 0 \=\= ' '; and check the type we will return true.
if we set 0 \=\=\=' '; then we will return false because triple equals also ensure the underlying types are the same.