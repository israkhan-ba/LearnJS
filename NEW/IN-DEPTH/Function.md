# Functions


## What is a function
Function is a way to make codes reusable.  
It let you group a series of statements together  
to perform a specific task and easily to call them.

## Why we use a function
Codes can be complex, and without functions  
you need to rewrite codes repeatedly to perform a certain task.
Then function will helps you leverage works out
and make it easily to maintain.


### 4 main kind of function
1. No parameter, no output returns.
2. No parameter,
ve some output returns.
3. Have parameter, no output returns.
4. Have parameter, have some output returns.

Some function may require a parameter to work, some might not.

## How to create and use a function
### Function Declaration (Simple)  
#### Function structure
- function keyword  
- function name  
- function parameter  
- return value  

> *`function`* `functionName(`*`Parameters`*`){`  
> &nbsp;&nbsp;&nbsp;`statement 1;`  
> &nbsp;&nbsp;&nbsp;`statement 2;`  
> &nbsp;&nbsp;&nbsp;...  
> &nbsp;&nbsp;&nbsp;`statement n;`  
>`}`

##### Example.
> *`function`* `functionName(`*`WriteSomething`*`){`  
> &nbsp;&nbsp;&nbsp;`console.log(WriteSomething);`  
>`}`


#### Invoking (Calling) the basic function
> `functionName(`*`Parameter`*`);`


##### Calling example
Example #1
> ```
> testFunction();
> ```

Example #2
> ```
> testFunction("Hello");
> ```
> // This will show "Hello" in console as an output.

#### Create a function as a variable
```
var variableFunction = function(PARAMETER){
    // do something
}
```

##### Example

```
var testVarFunction = function(WriteSomething){
    console.log(WriteSomething);
}
```
Calling variable function test

```    
testVarFunction();
testVarFunction("This is a variable function");
```