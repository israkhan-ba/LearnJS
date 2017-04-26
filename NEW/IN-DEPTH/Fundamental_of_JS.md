# Fundamental of JavaScript

In this page, it will explain shortly about all of the JavaScript fundamental elements and concepts which will set a quick overview for the very basic of JavaScript

And it will be recommended to re-read this page frequently as it could help you understand and get clarify with JavaScript quickly.

So its very intention is to make you less confuse.


## Syntax

Syntax is a set of rules that defined how a program are constructed.  

Programming is **instructions** that listing well so a computer can be executed, and each program instructions are called generally called **statements**, So basically we can call any program is a set and sequence of statements working together

And we have **expressions**, which is any valid set of literals, variables, operators and expressions that evaluates to a single value.

In JavaScript **expressions** and **statements** are distinguished.    
For short, an **expression** produces a value and a **statement** performs an action.


### Statement

**Statements** are using to do something or produce some behavior and they will cause some side effects, so we can basically categorize statements by their kinds of side effect.

Basically each statements are seperated by a semicolon ( **;** )

---

### Expression

**Expression** intended to produces or evaluates some value without any side effect, the value may be a number, a string, or a logical value. Conceptually, there are two main type of expressions: those that assign a value to a variable, and those that simply have a value.

---


### Expression statement

If any expression that have produces side effect we will called them Expression statements.

Because **statements** can contain **expression** so wherever JavaScript expects a statement, we can also write an expression in to that but not a vice versa (we can't write a statement where JavaScript expects an expression)

---

### Code block
A block set that use to group statements , expression and declaration together (and can be zero statement either), functions, or if statement are some sort of block statements

In JavaScript, Blocks can be nested in any block.

---

### Values & Data Types
Everything in computer is just data (and yes only data) and each and every data has its own role.

Most of data are seperated to things called value, so values are some thing that represent some kind of data which will be stored in some way (like in memory).

And each value have a type, which determines the kind of role it can play.

In JavaScript there are basically 6 data types, which catagorized as 3 categories.  
**Primitive Data Types**, **Special Data Types** and **Composite Data Types**

#### Primitive Data Types
- **Number**  
One of three primitive data types which represented numbers  
For short, we can defined numbers by using numerical character (0-9) , using dot ( . )  for floating point ( ex. 12345.67890 )
and using operators symbol for calculation  ( + , - , * , / , % )


- **String**
A primitive data type using for contain any words, phases, or sentence  
So we can defined strings by using Quotes ( ' ' ) or Double Quotes ( " " ) and some string in between them.


- **Boolean**  
Another primitive data type that play the logical part. Values of boolean are very simple, just `true` and `false` but they're playing a big part in all application.

#### Special Data Types

- **Null**  
A trivial data type that define only a single but special value which meaning "no value" its type is actually an object. So you can declare any variable and set it to null, then when it's printed out, you'll see "null" rather of "undefined"


- **Undefined**  
Another trivial data type which you don't need to do anything expect just not assign any value to variables, or put simply it's means that a variable has been declared but no value exists.
**Undefined** is not an object data type, it's a primitive type, and is a type of *`undefined`* itself.

#### Composite Data Types

- **Object** (Data type) 
An object datatype, in computer science, is a value in memory which is possibly referenced by an identifier.
It is a data type which is collecion of properties

---

### Variable

Variable is a container that used for storing data

In JavaScript, Variable are declared by using `var` key word (Also we can initialize variable with values but it's not necessary to use `var` key word)

---

### Identifier

An identifier is a sequence of characters, or simply a name, in the code that provide label for identifies a variable, function, or property for reuse.
It's differs from stings in that strings are data, while identifiers is part of the code.  

_In JavaScript, there is no way to convert identifiers to strings, but sometimes it is possible to parse strings into identifiers._

Identifier naming examples
>  i  
> my_variable_name  
> v13  
> _dummy  
> $str  

Unicode escape sequences are also allows in JavaScript ECMAScript to appear in identifiers.

Finally, identifiers cannot be the same as any of the keywords used for other purposes in JavaScript. The next section lists the special names that are reserved in JavaScript.

#### Rules of Identifier

##### Variables, Functions and Properties

- Case-sensitive : a and A is different


- Start only with ` $ ` (dolla sign) , letters (ascii, unicode) , *` _ `*   (underscore)  
numbers and other signs are not allowed

##### Reserved Keywords

In JavaScript, there are words in the syntax that reserved for specific purposes which they're not available to use to name any declaration, but it's possible to use these word as a part of a name, but it's not recommended for a good reason.

###### Declaration

 - *`var`*  
 
 - *`function`*  
 
 - *`new`*  
 
###### Conditional
 
 
 - *`if`*    
 
 - *`else`*  
 
 - *`elseif`*  


  
 - *`switch`*  
 
 - *`case`*  
 
 - *`default`*  
 
 - *`break`*  


###### Loops
 
 - *`for`*
 
 - *`in`*
 
 - *`do`*
 
 - *`while`*
 
 - *`continue`*
 
 
###### Validation
 
 - *`try`*
 
 - *`throw`*
 
 - *`catch`*
 
 - *`finally`*
 
 
###### Operators

 - *`typeof`*

 - *`instanceof`*

 - *`this`*

 - *`delete`*

 - *`void`*

###### Statements

 - *`return`*
 
 - *`with`*
 
##### Reserved words
 
###### Nonstrict mode

 - *`class`*
 - *`const`*
 - *`enum`*
 - *`export`*
 - *`extends`*
 - *`import`*
 - *`super`*
 
###### `'use strict'` mode

 - *`implements`*
 - *`interface`*
 - *`let`*
 - *`package`*
 - *`private`*
 - *`public`*
 - *`protected`*
 - *`static`*
 - *`yield`*
 
##### Variables

###### Local scope
 - *`var`* `a`
 
###### Global scope
 - *`a = 123`*
 
 ---

### Operators


List of operator types
- Arithmetic Operators
 Perform arithmetic with each values and/or variables

- Assignment Operators
 Assign values or variables

- String Operators
 Concatenate strings (add or join them together) 
 
- Comparison Operators
 Determine difference or equality between variables or values in logical statements

- Conditional (Ternary) Operator
 Assign a value to a variable based on a condition

- Logical Operators
 Determine logics between variables or values

- Bitwise Operators


- `typeof` Operator
 Check and returns the type of a variable, function, expression or object.

- `delete` Operator
 Delete a property from an object
 
- `in` Operator
 Check and returns true if the specified property is in the specified object, otherwise false.

- `instanceof` Operator
 Check and returns true if the specified object is an instance of the specified object.

- `void` Operator
  Evaluates an expression and returns undefined. This operator is often used to obtain the undefined primitive value, using "void(0)" (useful when evaluating an expression without using the return value)
 
---

### Function
 A set of statements that can be executed together and reusable, in JavaScript it is more special as functions are first-class objects which mean we can use any function as a value like others data types, so we can do (almost) everything to them, e.g. Assigning them to variables, Pass them as arguments to other functions, return another function from them. , So these are powerful ways to use them.

 JavaScript functions are full fledged objects, often called first-class objects[1], having properties and methods, mutable values, and dynamic memory.

#### Basic JavaScript Function
 Like any other programming languages, we use functions in JavaScript to do something that can be reuse again and sometimes we can use it to produce different output then it's needs to tell the function in some way.
 
##### Create a function
 We create a function by defining it, the most basic and simpliest way to do is using the `function` keyword
 
 >*`function`*
 
 then follow with a function name which we could call it later when we need
 
 *it's a practice called **Camel Case** which is a common way to name functions or variables in programming, where each word will start with capital letter, in this specific style is called lower camel case which initial lower case letter.*
 
 > `function` *`doSomething`* 

 and we need `()` a pair of parenthesis signs after the name

 > `function doSomething` *`()`*
 
 and follow with `{}` a pair of brackets signs after that

 > `function doSomething ()` `{}`
 
 Now we have a new function which basically doing nothing
 so we need to program the function to have a set of statement
 and we do write all of it inside the brackets sign like this

 > `function doSomething () {`  
 > &nbsp;&nbsp;&nbsp;&nbsp;
 > *`// Something to do here`*  
 > `}`

 And if we want the function to deal with something differently, then we could tell them by make them having **_parameters_** inside the parenthesis which will effect codes inside the function, and we can have any number of parameter by seperate each of them with **_`,`_** _`comma`_

 > `function doSomething (` *__`param1,`__* *`param2, paramN`* `) {`  
 > &nbsp;&nbsp;&nbsp;&nbsp;
 > *`// Something to do here`*  
 > `}`
 
##### Execute a function

Functions is created intended to be reuse at any time somewhere inside of our code, so we need to call them after we create them, the most basic way to call a function is using the function name follow with parenthesis, and it's case-sensitive

 > *`doSomething()`*
 
#### Anatomy of JavaScript functions

##### Function body
 Generally speaking, a function is a "subprogram" that can be called by code external (or internal in the case of recursion) to the function. Like the program itself, a function is composed of a sequence of statements called the function body. Values can be passed to a function, and the function will return a value.

##### Function arguments
 The parameters of a function call are the function's arguments. Arguments are passed to functions by value. If the function changes the value of an argument, this change is not reflected globally or in the calling function. However, object references are values, too, and they are special: if the function changes the referred object's properties, that change is visible outside the function

##### `return` statement
 To return a value other than the default, a function must have a return statement that specifies the value to return. A function without a return statement will return a default value. In the case of a constructor called with the new keyword, the default value is the value of its this parameter. For all other functions, the default return value is undefined.


#### Defining Functions

##### Named function declaration

**_Code Examples_**
 
>```
> function sum(num1,num2) {  
>     return num1 + num2;
> }
>```

##### Variable Assignment function expression
 
**_Code Examples_**
* **_Named Function_** 
>```
> var sum = function add(num1,num2) {
>     return num1 + num2;
> };
>```

* **_Anonymous Function_**
>```
> var sum = function(num1, num2) {
>     return num1 + num2;
> };
>```

##### Immediately Invoked function expression

**_Code Examples_**
* **_Named Function_** 
>```
> (function sum(num1, num2) {
>      return num1 + num2;
> }(1, 2));
>```

* **_Anonymous Function_**
>```
> (function(num1, num2) {
>        return num1 + num2;
> }(1, 2));
>```

##### Assigned and Invoked function expression

**_Code Examples_**
* **_Named Function_** 
>```
> var sum = function add(num1, num2) {
>         return num1 + num2;
>}(1, 2);
>```

* **_Anonymous Function_**
>```
> (function(num1, num2) {
>      return num1 + num2;
> }(1, 2));
>```

##### Property Assignment

**_Code Examples_**
* **_Named Function_** 
>```
> var obj1 = {
>    sum: function add(num1, num2) {
>        return num1 + num2
>    }
> };
>```

* **_Anonymous Function_**
>```
> var obj2 = {
>    sum: function(num1, num2) {
>        return num1 + num2
>    }
> };
>```

##### Passed as Argument

**_Code Examples_**
* **_Named Function_** 
>```
> window.setTimeout(<strong>function add() {
>    alert(1 + 2);
> }</strong>, 500);
>```

* **_Anonymous Function_**
>```
> window.setTimeout(<strong>function() {
>      alert(1 + 2);
> }</strong>, 500);
>```

##### Returned (closure)

**_Code Examples_**
* **_Named Function_** 
>```
> function counter() {
>    var count = 0;
>        return function c() {
>            alert(count++);
>        }
> }
>```

* **_Anonymous Function_**
>```
> function counter() {
>    var count = 0;
>        return function() {
>            alert(count++);
>        }
> }
>```

##### Arrow Functions

**_Code Examples_**
* **_Anonymous Function_** 
>```
> var sum = (num1, num2) => {
>    return num1 + num2
> };
>```

* **_Anonymous w/out optional bracketed return_** 
>```
> var sum = (num1, num2) => num1 + num2; 
>```

#### Function Constructor

##### Construct a function

**_Code Examples_**
>```
> var sum = new Function('num1', 'num2', 'return num1 + num2');
>``` 

##### Constructor w/apply()

**_Code Examples_**
>```
> var args = ['num1', 'num2', 'return num1 + num2'];
> var sum = Function.apply(this, args);
>```

##### Immediately Invoked Constructor w/apply()

**_Code Examples_**
>```
> var args = ['num1', 'num2', 'return num1 + num2'];
> Function.apply(this, args)
>         .apply(this, [1, 2]);
>```

---

### Objects
  
#### Object (itself) 
 JavaScript Objects are collecion of properties and methods which will be contained inside curly brackets `{ }` in the format of `key : value` paring   
 
 _You can contain any data types in an object, also nest objects and arrays within._

#### Array (intrinsic object)
 A container-like value which is an object data type, it's can contain values serially in an index manner which we call them elements, start counting each elements from index 0, and when there are changes in an array, it will resort the index number.  
 
 _You can contain any data types in an array, also nest it with other arrays or objects._

#### Function object
 
 
#### Math object
 Perform mathematical tasks.
 
 _Math is not a constructor. All properties/methods of Math can be called by using Math as an object, without creating it._

#### Date object
 Work with dates and times.
 Date objects are created with new Date().

#### RegExps
 Describes a pattern of characters. Perform pattern-matching and "search-and-replace" functions on text.
