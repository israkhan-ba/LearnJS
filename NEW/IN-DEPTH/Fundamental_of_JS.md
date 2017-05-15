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

List of Operators
- **Assignment Operators**  
 Assign values or variables
 
- **Arithmetic Operators**  
 Perform arithmetic with each values and/or variables

- **Comparison Operators**  
 Determine difference or equality between variables or values in logical statements
 
- **Logical Operators**  
 Determine logics between variables or values
 
- **Conditional (Ternary) Operator**  
 Assign a value to a variable based on a condition
 
- **String Operators**  
 Concatenate strings (add or join them together) 
 
- **Bitwise Operators**  


- **Comma Operator**  


- **Unary Operators**  


- **Relational Operators**


### Assignment Operators
 An assignment operator assigns a value to its left operand based on the value of its right operand.
 The basic assignment operator is equal (=), which assigns the value of its right operand to its left operand.

#### Assignment ( = )
 Simple assignment operator which assigns a value to a variable. The assignment operation evaluates to the assigned value. Chaining the assignment operator is possible in order to assign a single value to multiple variables.
 
**_Syntax_**
> *Operator:* `x` **`=`** `y`

**_Code Examples_**
>```
> // Assuming the following variables
> //  x = 5
> //  y = 10
> //  z = 25
> 
> x = y     // x is 10
> x = y = z // x, y and z are all 25
>```


#### Addition Assignment ( += )

 The addition assignment operator adds the value of the right operand to a variable and assigns the result to the variable. The types of the two operands determine the behavior of the addition assignment operator. Addition or concatenation is possible.

**_Syntax_**
> *Operator:* `x` **`+=`** `y`  
> *Meaning:*  `x  = x + y`

**_Code Examples_**
>```
> // Assuming the following variables  
> //  foo = 'foo'  
> //  bar = 5  
> //  baz = true  
>  
> 
> // Number + Number -> addition
> bar += 2 // 7
> 
> // Boolean + Number -> addition
> baz += 1 // 2
> 
> // Boolean + Boolean -> addition
> baz += false // 1
> 
> // Number + String -> concatenation
> bar += 'foo' // "5foo"
> 
> // String + Boolean -> concatenation
> foo += false // "foofalse"
> 
> // String + String -> concatenation
> foo += 'bar' // "foobar"
>```


#### Subtraction Assignment ( -= )

 The subtraction assignment operator subtracts the value of the right operand from a variable and assigns the result to the variable.
 
**_Syntax_**
> *Operator:* `x` **`-=`** `y`  
> *Meaning:*  `x  = x - y`

**_Code Examples_**
>```
> // Assuming the following variable
> //  bar = 5
> 
> bar -= 2     // 3
> bar -= 'foo' // NaN
>```


#### Multiplication Assignment ( *= )

 The multiplication assignment operator multiplies a variable by the value of the right operand and assigns the result to the variable.

### Arithmetic Operators


### Comparison Operators


### Logical Operators


### Conditional (Ternary) Operator


### String Operators


### Bitwise Operators


### Comma Operator


### Unary Operators


### Relational Operators



 
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

 In JavaScript, All nonprimitive values are objects.
 The most common kinds of objects are Single (plain) objects, Arrays, and Regular Expressions


### Objects Characteristics


#### Compared by reference
Identities are compared; every value has its own identity:

**_Code Examples_**
>```
> > ({} === {})  // two different empty objects
> false
>  
> > var obj1 = {};
> > var obj2 = obj1;
> > obj1 === obj2
> > true
> >```


#### Mutable by default
You can normally freely change, add, and remove properties

**_Code Examples_**
>```
> > var obj = {};
> > obj.foo = 123; // add property `foo`
> > obj.foo
> 123
> >```


### Single Object 
 
 Like all values, objects have properties (or consider it as a set of properties)

 JavaScript Objects are collecion of properties and methods which will be contained inside curly brackets `{ }` in the format of `key : value` paring
 
 _You can contain any data types in an object, also nest objects and arrays within._

#### Object Literals
 So we can create an object (blank) directly using `{ }`
 
 **_Code Examples_**
>```
> var obj = { };
>
>```

and add (key, value) pair as properties and use a comma in between each pair  

 **_Code Examples_**
>```
> var obj = { 
>     key1: 'value1',
>     key2: 'valie2'
> };
>
>```

also functions can be added into objects and are called 'methods'

 **_Code Examples_**
>```
> var obj = { 
>     key1: 'value1',
>     key2: 'value2',
>     methodA: function() {
>       // do something
        console.log('This is methodA') // will show 'This is methodA' in the console
>     }
> };
>
>```

Here you can read ("get") an object's property by access it directly using `.` (dot operator)

 **_Code Examples_**
>```
> > obj.key1
> 'value1'
>
>```

And you can call its methods (Function-valued properties) just like this

 **_Code Examples_**
>```
> > obj.methodA()
> 'This is methodA'
>
>```

Read a property that doesn't exists will return the value `undefined`

 **_Code Examples_**
>```
> > obj.keyA
> undefined
>
>```

If you want to write ("set") new value to properties, it's simple just assign them directly

 **_Code Examples_**
>```
> > obj.key1 = 'New value for key 1'
> > obj.key1
> 'New value for Key 1'
>
>```

Check wether a property exists in an object using `in` operator

 **_Code Examples_**
>```
> > 'key1' in obj
> true
> 
> > 'keyA' in obj
> false
>
>```

More way to check that a property exist

 **_Code Examples_**
>```
> > obj.key1 !== undefined
> true
>
> > obj.keyA !== undefined
> false
>
>```

Remove a property is so simple using `delete` operator

 **_Code Examples_**
>```
> > delete obj.keyA
> true
>
> > 'keyA' in obj
> false
>
>```

##### Arbitrary Property Keys
 A property key can be any string. So far, we have seen property keys in object literals and after the dot operator. However, you can use them that way only if they are identifiers (see Identifiers and Variable Names). If you want to use other strings as keys, you have to quote them in an object literal and use square brackets to get and set the property: [Edit needed]

 **_Code Examples_**
>```
> > var obj = { 'not an identifier': 123 };
> > obj['not an identifier']
> 123
> > obj['not an identifier'] = 456;
>
>```

 Square brackets also allow you to compute the key of a property:

 **_Code Examples_**
>```
> > var obj = { hello: 'world' };
> > var x = 'hello';
> 
> > obj[x]
> 'world'
> > obj['hel'+'lo']
> 'world'
> 
>```


##### Nested object

You can nest any object inside an object by simply add them as values of properties

 **_Code Examples_**
>```
> var obj = { 
>     key1: 'value1',
>     key2: 'value2',
>     methodA: function() {
>       ...
>     },
      nestObj: {
        keyA: 'value of keyA'
      }
> };
>
>```

Accessing nested object properties and methods is also just add more dot operators and target keys

 **_Code Examples_**
>```
> > obj.nestObj.keyA
> 'value of keyA'
>
>```

#### Extracting Methods

If you extract a method, it loses its connection with the object. On its own, the function is not a method anymore, and this has the value undefined (in strict mode).

As an example, let’s go back to the earlier object jane:

 **_Code Examples_**
>```
> 'use strict';
> var jane = {
>     name: 'Jane',
> 
>     describe: function () {
>         return 'Person named '+this.name;
>     }
> };
>```

We want to extract the method describe from jane, put it into a variable func, and call it. However, that doesn’t work:

 **_Code Examples_**
>```
> > var func = jane.describe;
> > func()
> TypeError: Cannot read property 'name' of undefined
>```

The solution is to use the method bind() that all functions have. It creates a new function whose this always has the given value:

 **_Code Examples_**
>```
> > > var func2 = jane.describe.bind(jane);
> > func2()
> 'Person named Jane'
>```


#### Functions Inside a Method

Every function has its own special variable this. This is inconvenient if you nest a function inside a method, because you can’t access the method’s this from the function.

The following is an example where we call forEach with a function to iterate over an array:

 **_Code Examples_**
>```
> var jane = {
>     name: 'Jane',
>     friends: [ 'Tarzan', 'Cheeta' ],
>     logHiToFriends: function () {
>         'use strict';
>         this.friends.forEach(function (friend) {
>             // `this` is undefined here
>             console.log(this.name+' says hi to '+friend);
>         });
>     }
> }
>```

Calling logHiToFriends produces an error:

 **_Code Examples_**
>```
> > jane.logHiToFriends()
> TypeError: Cannot read property 'name' of undefined
>```

Let’s look at two ways of fixing this. First, we could store this in a different variable:

 **_Code Examples_**
>```
> logHiToFriends: function () {
>     'use strict';
>     var that = this;
>     this.friends.forEach(function (friend) {
>         console.log(that.name+' says hi to '+friend);
>     });
> }
>```

Or, forEach has a second parameter that allows you to provide a value for this:

 **_Code Examples_**
>```
> logHiToFriends: function () {
>     'use strict';
>     this.friends.forEach(function (friend) {
>         console.log(this.name+' says hi to '+friend);
>     }, this);
> }
>```

Function expressions are often used as arguments in function calls in JavaScript. Always be careful when you refer to this from one of those function expressions.


#### Constructors: Factories for Objects
 Until now, you may think that JavaScript objects are only maps from strings to values, a notion suggested by JavaScript’s object literals, which look like the map/dictionary literals of other languages. However, JavaScript objects also support a feature that is truly object-oriented: inheritance. This section does not fully explain how JavaScript inheritance works, but it shows you a simple pattern to get you started. Consult Chapter 17 if you want to know more.

 In addition to being “real” functions and methods, functions play another role in JavaScript: they become constructors—factories for objects—if invoked via the new operator. Constructors are thus a rough analog to classes in other languages. By convention, the names of constructors start with capital letters.

 **_Code Examples_**
>```
> // Set up instance data
> function Point(x, y) {
>     this.x = x;
>     this.y = y;
> }
> // Methods
> Point.prototype.dist = function () {
>     return Math.sqrt(this.x*this.x + this.y*this.y);
> };
>```

We can see that a constructor has two parts. First, the function Point sets up the instance data. Second, the property Point.prototype contains an object with the methods. The former data is specific to each instance, while the latter data is shared among all instances.
To use Point, we invoke it via the new operator:
 
 **_Code Examples_**
>```
> > var p = new Point(3, 5);
> p.x
> 3
> > p.dist()
> 5.830951894845301
>```

p is an instance of Point:
>```
> > p instanceof Point
> true
>```

### Array (intrinsic object)
 A container-like value which is an object data type, it's can contain values serially in an index manner (sequentially) which we call them elements, start counting each elements from index 0, and when there are changes in an array, it will resort the index number.  
 
 _You can contain any data types in an array, also nest it with other arrays or objects._

#### Array Literals
Array literals are handy for creating arrays:
> `> var arr = [ 'a', 'b', 'c' ];`

The preceding array has three elements: the strings `'a'`, `'b'`, and `'c'`.

You can access them via integer indices:

**_Code Examples_**
>```
> > arr[0]
> 'a'
> > arr[0] = 'x';
> > arr
> [ 'x', 'b', 'c' ]
>```

The `length` property indicates how many elements an array has.
You can use it to append elements and to remove elements:

**_Code Examples_**
>```
> > var arr = ['a', 'b'];
> > arr.length
> 2
>```
`
>```
> > arr[arr.length] = 'c';
> > arr
> [ 'a', 'b', 'c' ]
> > arr.length
> 3
>```
`
>```
> > arr.length = 1;
> > arr
> [ 'a' ]
>```

The `in` operator works for arrays, too:

**_Code Examples_**
>```
> > var arr = [ 'a', 'b', 'c' ];
> > 1 in arr // is there an element at index 1?
> true
> > 5 in arr // is there an element at index 5?
> false
>```

Note that arrays are objects and can thus have object properties:
**_Code Examples_**
>```
> > var arr = [];
> > arr.foo = 123;
> > arr.foo
> 123
>```


#### Array Methods
Arrays have many methods here are the list
- Copy elements using `slice()` method
**_Code Examples_**
>```
> > arr.slice(1, 2)
> [ 'b' ]
> > arr.slice(1)
> [ 'b', 'c' ]
>```

- Append an element using `push()` method
**_Code Examples_**
>```
> > arr.push('x')  
> > arr
> [ 'a', 'b', 'c', 'x' ] // append an element 4
>```

- Remove last element using `pop()` method
**_Code Examples_**
>```
> > arr.pop()
> 'x'
> > arr
> [ 'a', 'b', 'c' ] // the last element removed
>```


- Remove first element using `shift()` method
**_Code Examples_**
>```
> > arr.shift()  // remove first element
> 'a'
> > arr
> [ 'b', 'c' ]
>```

- Prepend an element using `unshift()` method
**_Code Examples_**
>```
> > arr.unshift('x')  // prepend an element
> 3
> > arr
> [ 'x', 'b', 'c' ]
>```


- Find the index of an element using `indexOf()` method
**_Code Examples_**
>```
> > arr.indexOf('b')  // find the index of an element
> 1
> > arr.indexOf('y')
> -1
>```


- All elements in a single string using `join()` method
**_Code Examples_**
>```
> > arr.join('-')  // all elements in a single string
> 'x-b-c'
> > arr.join('')
> 'xbc'
> > arr.join()
> 'x,b,c'
>```

#### Iterating over Arrays
There are several array methods for iterating over elements
The two most important ones are `forEach` and `map`.

- `forEach` iterates over an array and hands the current element and its index to a function:
**_Code Examples_**
>```
> [ 'a', 'b', 'c' ].forEach(
>     function (elem, index) {  // (1)
>         console.log(index + '. ' + elem);
>     });
>```

The preceding code produces the following output:
0. a
1. b
2. c

Note that the function in line (1) is free to ignore arguments.
It could, for example, only have the parameter `elem`.

- `map` creates a new array by applying a function to each element of an existing array:
**_Code Examples_**
 >```
 > > [1,2,3].map(function (x) { return x*x })
 > [ 1, 4, 9 ]
 >```
>

### Regular Expression (RegExps)
 Describes a pattern of characters. Perform pattern-matching and "search-and-replace" functions on text.

JavaScript has built-in support for regular expressions.   

They are delimited by slashes:
>```
> /^abc$/
> /[A-Za-z0-9]+/
>```

Method test(): Is There a Match?
>```
> > /^a+b+$/.test('aaab')
> true
> > /^a+b+$/.test('aaa')
> false
>```

Method exec(): Match and Capture Groups
>```
> /a(b+)a/.exec('_abbba_aba_')
[ 'abbba', 'bbb' ]
>```

The returned array contains the complete match at index 0, the capture of the first group at index 1, and so on. There is a way to invoke this method repeatedly to get all matches.

Method replace(): Search and Replace
>```
> > '<a> <bbb>'.replace(/<(.*?)>/g, '[$1]')
> '[a] [bbb]'
>```

The first parameter of replace must be a regular expression with a /g flag; otherwise, only the first occurrence is replaced. There is also a way to use a function to compute the replacement.


## Standard built-in objects

### Math
 Math is an object with arithmetic functions to perform mathematical tasks.
 
 _Math is not a constructor. All properties/methods of Math can be called by using Math as an object, without creating it._

**_Code Examples_**
>```
> > Math.abs(-2)
> 2
> 
> > Math.pow(3, 2)  // 3 to the power of 2
> 9
> 
> > Math.max(2, -1, 5)
> 5
> 
> > Math.round(1.9)
> 2
> 
> > Math.PI  // pre-defined constant for π
> 3.141592653589793
> 
> > Math.cos(Math.PI)  // compute the cosine for 180°
> -1
>```

### Date
 Work with dates and times in JavaScript.   
 by Date constructor so you can parsing, managing, and displaying dates.
 
#### The Date Constructor

There are four ways of invoking the constructor of `Date`

