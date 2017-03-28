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
Host object (provided by the JS environment)
          : Implementation-dependent
Function object (implements [[Call]] in ECMA-262 terms)                    : "function"
Any other object : "object"

#### Examples

