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


### Statements

**Statements** are using to **do** something or produce some behavior and they will cause some side effects, so we can basically categorize statements by their kinds of side effect.

Basically each statements are seperated by a semicolon ( **;** )

For examples
- Declaration of variables and functions
> *`var`* `x`;

- Using keywords to do something
 * Create code blocks using `if`...`else` statements
 > *`if (`* `x >= 0` *`) {`*
 >          // do something here
 > *`} else {`*
 >          // do something else
 > *`}`*

---

### Expression

**Expression** intended to **produces** or evaluates some value without any side effect, the value may be a number, a string, or a logical value. Conceptually, there are two main type of expressions: those that assign a value to a variable, and those that simply have a value.

For example
- Simple expression
>```
> 3 * 7
>```

- **if-then-else** as an expression
> *`var`* `x =` **` y >= 0 ? y : -y;`**

---


### Expression statement

If any expression that have produces side effect we will called them Expression statements.

Because **statements** can contain **expression** so wherever JavaScript expects a statement, we can also write an expression in to that but not a vice versa (we can't write a statement where JavaScript expects an expression)

For example
>```
> foo(7, 1);
>```

The whole line is a statement (a so-called expression statement), but the function call foo(7, 1) is an expression.

---

### Semicolons
Semicolons terminate statements, but not blocks.

Semicolons are optional in JavaScript.

There is one case where you will see a semicolon after a block: a function expression is an expression that ends with a block. If such an expression comes last in a statement, it is followed by a semicolon
> `// Pattern: var _ = ___;`  
> `var x = 3 * 7;`  
> `var f = function () { };  // function expr. inside var decl.`  

#### Automatic Semicolon Insertion
The goal of automatic semicolon insertion (ASI) is to make semicolons optional at the end of a line.

The image invoked by the term *automatic semicolon insertion* is that the JavaScript parser inserts semicolons for you (internally, things are usually handled differently).

Put another way, ASI helps the parser to determine when a statement ends. Normally, it ends with a semicolon.

ASI dictates that a statement also ends if:
- A line terminator (e.g., a newline) is followed by an illegal token.
- A closing brace is encountered.
- The end of the file has been reached.


### Comments
JavaScript has two kinds of comments: single-line comments and multiline comments.

**Single-line** comments start with **//** and are terminated by the end of the line:

> `x++;` **`// single-line comment`**

**Multiline** comments are delimited by **/*** and ***/**:
> **`/\* This is`  
> `a multiline`  
> `comment.`  
> `\*/**`


### Code block
A block set that use to group statements , expression and declaration together (and can be zero statement either), functions, or if statement are some sort of block statements

In JavaScript, Blocks can be nested in any block.

---

## Values & Data Types
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

## Variable

Variable is a container that used for storing data

In JavaScript, Variable are declared by using `var` key word (Also we can initialize variable with values but it's not necessary to use `var` key word)

Variables in JavaScript are declare using `var` statement

>```
> var foo;  
> foo = 3; // OK, has been declared  
> bar = 5; // not OK, an undeclared variable  
>```


You can also combine a declaration with an assignment, to immediately initialize a variable:

>```
> var foo = 3;  
>```


The value of an uninitialized variable is undefined:

>```
> > var x;  
> > x  
> undefined  
>```


#### Static Versus Dynamic

There are two angles from which you can examine the workings of a program:

Statically (or lexically)
You examine the program as it exists in source code, without running it. Given the following code, we can make the static assertion that function g is nested inside function f:

>```
> function f() {  
>    function g() {  
>    }  
> }  
>```


The adjective lexical is used synonymously with static, because both pertain to the lexicon (the words, the source) of the program.


Dynamically
You examine what happens while executing the program (“at runtime”). Given the following code:

>```
> function g() {  
> }  
> function f() {  
>     g();  
> }  
>```


when we call f(), it calls g(). During runtime, g being called by f represents a dynamic relationship.

#### The Scope of a Variable

The scope of a variable are the locations where it is accessible. 
For example:

> ```
> function foo() {  
>     var x;  
> }  
>```


Here, the direct scope of x is the function foo().


- Lexical scoping  
Variables in JavaScript are lexically scoped, so the static structure of a program determines the scope of a variable (it is not influenced by, say, where a function is called from).


- Nested scopes  
If scopes are nested within the direct scope of a variable, then the variable is accessible in all of those scopes:



>```
> function foo(arg) {  
>    function bar() {  
>        console.log('arg: '+arg);  
>    }  
>    bar();  
> }  
> console.log(foo('hello')); // arg: hello  
>```  


The direct scope of arg is foo(), but it is also accessible in the nested scope bar(). With regard to nesting, foo() is the outer scope and bar() is the inner scope.


- Shadowing  
If a scope declares a variable that has the same name as one in a surrounding scope, access to the outer variable is blocked in the inner scope and all scopes nested inside it. Changes to the inner variable do not affect the outer variable, which is accessible again after the inner scope is left:

>```
> var x = "global";  
> function f() {  
>    var x = "local";  
>    console.log(x); // local  
> }  
> f();  
> console.log(x); // global  
>```


Inside the function f(), the global x is shadowed by a local x.


#### Variables Are Function-Scoped

JavaScript’s variables are function-scoped: only functions introduce new scopes; blocks are ignored when it comes to scoping.

For example:
>```
> function main() {  
>     { // block starts  
>         var foo = 4;  
>     } // block ends  
>     console.log(foo); // 4  
> }  
>```


Put another way, `foo` is accessible within all of `main()`, not just inside the block.


#### Variable Declarations Are Hoisted

JavaScript hoists all variable declarations, it moves them to the beginning of their direct scopes. This makes it clear what happens if a variable is accessed before it has been declared:

>```
> function f() {  
>    console.log(bar);  // undefined  
>    var bar = 'abc';  
>    console.log(bar);  // abc  
> }  
>```


We can see that the variable bar already exists in the first line of f(), but it does not have a value yet; that is, the declaration has been hoisted, but not the assignment. JavaScript executes f() as if its code were:

>```
> function f() {  
>    var bar;  
>    console.log(bar);  // undefined  
>    bar = 'abc';  
>    console.log(bar);  // abc  
> }  
>```


If you declare a variable that has already been declared, nothing happens (the variable’s value is unchanged):

>```
> > var x = 123;  
> > var x;  
> > x  
> 123  
>```


Each function declaration is also hoisted, but in a slightly different manner. The complete function is hoisted, not just the creation of the variable in which it is stored 


#### Global Variables
The scope containing all of a program is called global scope or program scope. This is the scope you are in when entering a script (be it a < script > tag in a web page or be it a .js file). Inside the global scope, you can create a nested scope by defining a function. Inside such a function, you can again nest scopes. Each scope has access to its own variables and to the variables in the scopes that surround it. As the global scope surrounds all other scopes, its variables can be accessed everywhere:


>```
> // here we are in global scope
> var globalVariable = 'xyz';
> function f() {
>     var localVariable = true;
>     function g() {
>         var anotherLocalVariable = 123;
> 
>         // All variables of surround scopes are accessible
>         localVariable = false;
>         globalVariable = 'abc';
>     }
> }
> // here we are again in global scope
>```


---

## Identifier

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
 
 ---

## Operators


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

## Function
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
 
 and we can pass arguments to is as it was defined using parameters

 > `doSomething(` *__`arg1,`__* *`arg2, argN`* `)`
 
#### Anatomy of JavaScript functions

##### Function body
 Generally speaking, a function is a "subprogram" that can be called by code external (or internal in the case of recursion) to the function. Like the program itself, a function is composed of a sequence of statements called the function body. Values can be passed to a function, and the function will return a value.

##### Function arguments
 The parameters of a function call are the function's arguments. Arguments are passed to functions by value. If the function changes the value of an argument, this change is not reflected globally or in the calling function. However, object references are values, too, and they are special: if the function changes the referred object's properties, that change is visible outside the function

##### `return` statement
 To return a value other than the default, a function must have a return statement that specifies the value to return. A function without a return statement will return a default value. In the case of a constructor called with the new keyword, the default value is the value of its this parameter. For all other functions, the default return value is undefined.


#### Defining Functions

##### Named function declaration

This is the most classic and oldest way that we are familiar with in JavaScript, probably one of the first thing we do in the early day of our JavaScript learning.

In **named function declaration** we have to know that there are few things to get cleared as these concept will help you understand a lot more in the future.

1. Function declaration must have names
That's mean in this method, you can't basically create anomymous functions, they're need to have an identifier.

2. Can't declare functions in `if` statements

3. Functions declaration are Hoisted
For short you can call the functions before they are created in the code. The entire function get hoisten to the top of its containing scope

*You can learn more in-depth in*  
- Hoisting Concept
- Scoping Concept 


**_Code Examples_**
 
>```
> function sum(num1,num2) {  
>     return num1 + num2;
> }
>``` 

##### Variable Assignment function expression
 
 This is functionally equivalent to the Function Declaration above, except this variation is NOT hoisted.
 
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

This function is immediately invoked, meaning that it is defined and called at the same time. The function's name is only available within its execution scope (defined by the parentheses), so it cannot be called later in the program.

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

This is a combination of the variable assignment expression and the immediately invoked function (both demonstrated above).

One neat application for the named variety of this is to make recursive functions more readable, by substituting arguments.callee with your function name.

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

By assigning functions (either named or unnamed) to properties of objects, we define methods on those objects. This has many applications in object oriented programming. We can also use this to namespace our functions, and keep them out of the global scope.

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

Function names in ECMAScript are nothing more than variables, meaning we can pass them around like variables. Many methods (like setTimeout()) take functions as arguments. This is a common pattern for defining callbacks.

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

Functions can be returned from other functions. 

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

## Objects
  
#### Object (itself) 
 JavaScript Objects are collecion of properties and methods which will be contained inside curly brackets `{ }` in the format of `key : value` paring   
 
 _You can contain any data types in an object, also nest objects and arrays within._

### Array (intrinsic object)
 A container-like value which is an object data type, it's can contain values serially in an index manner (sequentially) which we call them elements, start counting each elements from index 0, and when there are changes in an array, it will resort the index number.  
 
 _You can contain any data types in an array, also nest it with other arrays or objects._

#### Array Literals
Array literals are handy for creating arrays:
> `> var arr = [ 'a', 'b', 'c' ];`

The preceding array has three elements: the strings 'a', 'b', and 'c'.

You can access them via integer indices:

**_Code Examples_**
>```
> > arr[0]
> 'a'
> > arr[0] = 'x';
> > arr
> [ 'x', 'b', 'c' ]
>```

The length property indicates how many elements an array has.
You can use it to append elements and to remove elements:


#### Function object
 
 
#### Math object
 Perform mathematical tasks.
 
 _Math is not a constructor. All properties/methods of Math can be called by using Math as an object, without creating it._

#### Date object
 Work with dates and times.
 Date objects are created with new Date().

#### RegExps
 Describes a pattern of characters. Perform pattern-matching and "search-and-replace" functions on text.
