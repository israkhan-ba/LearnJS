# Arrays
Arrays are special type of variable, contain lists of multiple values, serialize them and index by number starting from 0.
Values in an array can be variuos type. Numbers, Strings, Booleans, or even Objects and Arrays themselves.

It is an object which have methods and properties of it's own.

Array should be used to represents a list of a set of values that are related to each other.

## How to use Array

#### Creating an array
1. Using Array Literal
> `var array =`** `[value1, value2, value3, ..., valueN]`**`;`

2. Using Array Constructor (Not recommended)
> `var array =`** `new Array(value1, value2, value3, ..., valueN]`**`;`

#### Accessing value in Array
Using **[**...**]** (Brackets) after variable that an array is associate
> `array`**`[0]`** will return the value of the array at index 0

#### Array properties and methods
First, for example, we set an array and assign values to it.
> `myArray = ["Value1", true, 3, "4", "Five"]`

- .length - Return how many value stored in the array.
> `console.log(myArray.length);`  
> // Will show **5** in console  
>
> Using .length to return specific value by array index  
> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 
> `console.log(myArray[myArray.length - 1]);`  
> // Will show **Five** in console which is the last value of the array.
>
> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 
> `console.log(myArray[myArray.length - 2]);`  
> // Will show **4** in console which is the second from the last value of the array.