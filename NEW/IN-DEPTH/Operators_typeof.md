# typeof Operator

typeof Operator is used to get the data type of its operand.

### Using typeof
> `typeof targetVariable;`

Example
> ```
> var x = 10;
> typeof x;  
> ```
> // This will return `number`

Example 2
> ```
> var x = "Some String";```
> **`typeof`** `x;`
>   
> // This will return **`string`**

### Possible return values of typeof (Will be shown as Type:Result)

Undefined : "undefined"  
Null	  : "object" (see below)  
Boolean	  : boolean"  
Number    : "number"  
String	  : "string"  
Symbol (new in ECMAScript 2015)	             : "symbol"  
Host object 
          : Implementation-dependent  
(provided by the JS environment)  
Function object                     : "function"   
(implements [[Call]] in ECMA-262 terms)  
Any other object : "object"  

#### Examples

> // Numbers  
typeof 37 === 'number';  
typeof 3.14 === 'number';  
typeof(42) === 'number';  
typeof Math.LN2 === 'number';  
typeof Infinity === 'number';  
typeof NaN === 'number'; //   Despite being "Not-A-Number"  
typeof Number(1) === 'number'; // but never use this form!

> // Strings  
typeof '' === 'string';  
typeof "bla" === 'string';  
typeof (typeof 1) === 'string'; // typeof always returns a string  
typeof String('abc') === 'string'; // but never use this form! 

> // Booleans
typeof true === 'boolean';  
typeof false === 'boolean';  
typeof Boolean(true) === 'boolean'; // but never use this form!  