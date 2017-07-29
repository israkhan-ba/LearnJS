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
 
**_Syntax_**
> *Operator:* `x` **`*=`** `y`  
> *Meaning:*  `x  = x * y`
 
**_Code Examples_**
>```
> // Assuming the following variable
> //  bar = 5
> 
> bar *= 2     // 10
> bar *= 'foo' // NaN
>```


#### Division Assignment ( /= )

 The division assignment operator divides a variable by the value of the right operand and assigns the result to the variable.

**_Syntax_**
> *Operator:* `x` **`/=`** `y`  
> *Meaning:*  `x  = x / y`
 
**_Code Examples_**
>```
> // Assuming the following variable
> //  bar = 5
> 
> bar /= 2     // 2.5
> bar /= 'foo' // NaN
> bar /= 0     // Infinity
>```


### Arithmetic Operators

 An arithmetic operator takes numerical values (either literals or variables) as their operands and returns a single numerical value. The standard arithmetic operators are addition (+), subtraction (-), multiplication (*), and division (/).
 These operators work as they do in most other programming languages when used with floating point numbers (in particular, note that division by zero produces Infinity). For example:
 

#### Addition Operator ( + )

 The addition operator produces the sum of numeric operands or string concatenation.

**_Syntax_**
> *Operator:* `x` **`+`** `y`

**_Code Examples_**
>```
> // Number + Number -> addition
> 1 + 2 // 3
> 
> // Boolean + Number -> addition
> true + 1 // 2
> 
> // Boolean + Boolean -> addition
> false + false // 0
> 
> // Number + String -> concatenation
> 5 + 'foo' // "5foo"
> 
> // String + Boolean -> concatenation
> 'foo' + false // "foofalse"
> 
> // String + String -> concatenation
> 'foo' + 'bar' // "foobar"
>```


#### Subtraction Operator ( - )

 The subtraction operator subtracts the two operands, producing their difference.

**_Syntax_**
> *Operator:* `x` **`-`** `y`

**_Code Examples_**
>```
> 5 - 3 // 2
> 3 - 5 // -2
> 'foo' - 3 // NaN
>```
 

#### Multiplication Operator ( * )

 The multiplication operator produces the product of the operands.

**_Syntax_**
> *Operator:* `x` **`*`** `y`

**_Code Examples_**
>```
> 2 * 2 // 4
> -2 * 2 // -4
> Infinity * 0 // NaN
> Infinity * Infinity // Infinity
> 'foo' * 2 // NaN
>```


#### Division Operator ( / )

 The division operator produces the quotient of its operands where the left operand is the dividend and the right operand is the divisor.

**_Syntax_**
> *Operator:* `x` **`/`** `y`

**_Code Examples_**
>```
> 1 / 2      // returns 0.5 in JavaScript
> 1 / 2      // returns 0 in Java 
> // (neither number is explicitly a floating point number)
> 
> 1.0 / 2.0  // returns 0.5 in both JavaScript and Java
> 
> 2.0 / 0    // returns Infinity in JavaScript
> 2.0 / 0.0  // returns Infinity too
> 2.0 / -0.0 // returns -Infinity in JavaScript
>```
 

#### Remainder Operator ( % )

 The remainder operator returns the remainder left over when one operand is divided by a second operand. It always takes the sign of the dividend, not the divisor. 

**_Syntax_**
> *Operator:* `var1` **`%`** `var2`

**_Code Examples_**
>```
> 12 % 5 // 2
> -1 % 2 // -1
> NaN % 2 // NaN
> 1 % 2 // 1
> 2 % 3 // 2
> -4 % 2 // -0
> 5.5 % 2 // 1.5
>```


#### Exponentiation Operator ( ** )

 The exponentiation operator returns the result of raising first operand to the power second operand. that is, var1var2, in the preceding statement, where var1 and var2 are variables. Exponentiation operator is right associative. a ** b ** c is equal to a ** (b ** c).
 
**_Syntax_**
> *Operator:* `var1` __`**`__ `var2`

**_Code Examples_**
>```
> 2 ** 3 // 8
> 3 ** 2 // 9
> 3 ** 2.5 // 15.588457268119896
> 10 ** -1 // 0.1
> NaN ** 2 // NaN
> 
> 2 ** 3 ** 2 // 512
> 2 ** (3 ** 2) // 512
> (2 ** 3) ** 2 // 64
>```
> To invert the sign of the result of an exponentiation expression:
>```
> -(2 ** 2) // -4
>```
> To force the base of an exponentiation expression to be a negative number:
>```
> (-2) ** 2 // 4
>```


#### Increment Operator ( ++ )

 The increment operator increments (adds one to) its operand and returns a value.

 - If used postfix, with operator after operand (for example, x++), then it returns the value before incrementing.
 - If used prefix with operator before operand (for example, ++x), then it returns the value after incrementing.

**_Syntax_**
> *Operator:* `x++ or ++x`

**_Code Examples_**
>```
> // Postfix 
> var x = 3;
> y = x++; // y = 3, x = 4
> 
> // Prefix
> var a = 2;
> b = ++a; // a = 3, b = 3
> >```


#### Decrement Operator ( -- )

 The decrement operator decrements (subtracts one from) its operand and returns a value.

 - If used postfix (for example, x--), then it returns the value before decrementing.
 - If used prefix (for example, --x), then it returns the value after decrementing.
 
**_Syntax_**
> *Operator:* `x-- or --x`

**_Code Examples_**
>```
> // Postfix 
> var x = 3;
> y = x--; // y = 3, x = 2
> 
> // Prefix
> var a = 2;
> b = --a; // a = 1, b = 1
>```


#### Unary Plus Operator ( + )

 The unary plus operator precedes its operand and evaluates to its operand but attempts to convert it into a number, if it isn't already. 
 
**_Syntax_**
> *Operator:* `+x`

**_Code Examples_**
>```
> +3     // 3
> +'3'   // 3
> +true  // 1
> +false // 0
> +null  // 0
> +function(val){  return val } // NaN
>```


#### Unary Negation Operator ( - )

 The unary negation operator precedes its operand and negates it.
 
**_Syntax_**
> *Operator:* `-x`

**_Code Examples_**
>```
> var x = 3;
> y = -x; // y = -3, x = 3
>```

**_Notes_**
- Although unary negation (-) also can convert non-numbers, unary plus is the fastest and preferred way of converting something into a number, because it does not perform any other operations on the number.

- It can convert string representations of integers and floats, as well as the non-string values true, false, and null.

- Integers in both decimal and hexadecimal ("0x"-prefixed) formats are supported. 

- Negative numbers are supported (though not for hex). If it cannot parse a particular value, it will evaluate to NaN.


### Comparison Operators - Equality

 JavaScript has both strict and type–converting comparisons. A strict comparison (e.g., ===) is only true if the operands are of the same type and the contents match. The more commonly-used abstract comparison (e.g. ==) converts the operands to the same type before making the comparison.


#### Equality Operator ( == )
 
 The equality operator converts the operands if they are not of the same type, then applies strict comparison. If both operands are objects, then JavaScript compares internal references which are equal when operands refer to the same object in memory.

**_Syntax_**
> *Operator:* `x` __`==`__ `y`

**_Code Examples_**
>```
>  1   ==  1        // true
> '1'  ==  1        // true
>  1   == '1'       // true
>  0   == false     // true
>  0   == null      // false
> var object1 = {'value': 'key'}, object2 = {'value': 'key'}; 
> object1 == object2 //false
> 
>  0   == undefined // false
> null  == undefined // true
>```


#### Inequality Operator ( != )

 The inequality operator returns true if the operands are not equal. If the two operands are not of the same type, JavaScript attempts to convert the operands to an appropriate type for the comparison. If both operands are objects, then JavaScript compares internal references which are not equal when operands refer to different objects in memory.

**_Syntax_**
> *Operator:* `x` __`!=`__ `y`

**_Code Examples_**
>```
> 1 !=   2     // true
> 1 !=  '1'    // false
> 1 !=  "1"    // false
> 1 !=  true   // false
> 0 !=  false  // false
>```
 

#### Identity / Strict Equality Operator ( === )

 The identity operator returns true if the operands are strictly equal (see above) with no type conversion. 

**_Syntax_**
> *Operator:* `x` __`===`__ `y`

**_Code Examples_**
>```
> 3 === 3   // true
> 3 === '3' // false
> var object1 = {'value': 'key'}, object2 = {'value': 'key'};
> object1 === object2 //false
>```
 

#### Non-Identity / Strict Inequality ( !== )

 The non-identity operator returns true if the operands are not equal and/or not of the same type. 

**_Syntax_**
> *Operator:* `x` __`!==`__ `y`

**_Code Examples_**
>```
> 3 !== '3' // true
> 4 !== 3   // true
>```


### Comparison Operators - Relational


#### Greater Than Operator ( > )

 The greater than operator returns true if the left operand is greater than the right operand.

**_Syntax_**
> *Operator:* `x` __`>`__ `y`

**_Code Examples_**
>```
> 4 > 3 // true
>```
 

#### Less Than Operator ( < )

 The less than operator returns true if the left operand is less than the right operand.

**_Syntax_**
> *Operator:* `x` __`<`__ `y`

**_Code Examples_**
>```
> 3 < 4 // true
>```
 

#### Greater Than or Equal Operator ( >= )

 The greater than or equal operator returns true if the left operand is greater than or equal to the right operand.

**_Syntax_**
> *Operator:* `x` __`>=`__ `y`

**_Code Examples_**
>```
> 4 >= 3 // true
> 3 >= 3 // true
>```


#### Less Than or Equal Operator ( <= )

 The less than or equal operator returns true if the left operand is less than or equal to the right operand.

**_Syntax_**
> *Operator:* `x` __`<=`__ `y`

**_Code Examples_**
>```
> 3 <= 4 // true
> 3 <= 3 // true
>```


### Logical Operators

 Logical operators are typically used with Boolean (logical) values. When they are, they return a Boolean value. However, the && and || operators actually return the value of one of the specified operands, so if these operators are used with non-Boolean values, they may return a non-Boolean value.
 
 If a value can be converted to true, the value is so-called truthy.
 If a value can be converted to false, the value is so-called falsy.

 Examples of expressions that can be converted to false are:
 - `null;`
 - `NaN;`
 - `0;`
 - `empty string ("");`
 - `undefined.`

 Even though the && and || operators can be used with operands that are not Boolean values, they can still be considered Boolean operators since their return values can always be converted to Boolean values.
 

#### Logical AND ( && )

**_Code Examples_**
>```
> a1 = true  && true      // t && t returns true
> a2 = true  && false     // t && f returns false
> a3 = false && true      // f && t returns false
> a4 = false && (3 == 4)  // f && f returns false
> a5 = 'Cat' && 'Dog'     // t && t returns "Dog"
> a6 = false && 'Cat'     // f && t returns false
> a7 = 'Cat' && false     // t && f returns false
> a8 = '' && false        // returns ""
> a9 = false && ||        // returns false
>```


#### Logical OR ( || )

**_Code Examples_**
>```
> o1 = true  || true       // t || t returns true
> o2 = false || true       // f || t returns true
> o3 = true  || false      // t || f returns true
> o4 = false || (3 == 4)   // f || f returns false
> o5 = 'Cat' || 'Dog'      // t || t returns "Cat"
> o6 = false || 'Cat'      // f || t returns "Cat"
> o7 = 'Cat' || false      // t || f returns "Cat"
> o8 = ''    || false      // returns false
> o9 = false || ''         // returns ""
>```


#### Logical NOT ( ! )

**_Code Examples_**
>```
> n1 = !true
> n2 = !false
> n3 = !'Cat'
>```


### Conditional (Ternary) Operator

 The conditional (ternary) operator is an operator to use for conditional as expression, it frequently used as a shortcut for the `if` statement.
 And it's the only operator that takes three operands.
 
 If condition is true, the operator returns the value of expr1; otherwise, it returns the value of expr2. 
 
**_Syntax_**
> condition ? expr1 : expr2 

**_Parameter_**
- `condition` (or `conditions`)  
An expression that evaluates to `true` or `false`.
- `expr1`, `expr2`  
Expressions with values of any type.

**_Code Examples_**
- **Basic usage**  
 Display a different message based on the value of the isMember variable.
 >```
 > 'The fee is ' + (isMember ? '$2.00' : '$10.00');
 >```

 Assign variables depending on a ternary result.
 >```
 > var elvisLives = Math.PI > 4 ? 'Yep' : 'Nope';
 >```
 
- **More advanced usage**  
 Multiple ternary evaluations_(the conditional operator is right associative)_.
 >```
 > var firstCheck = false,
 >     secondCheck = false,
 >     access = firstCheck ? 'Access denied' : 
 >              secondCheck ? 'Access denied' : 'Access granted'; 
 > console.log(access); // logs "Access granted"
 >```
 
 Use multiple conditions like in a multiple-conditions IF statement.
 >```
 > var condition1 = true,
 >     condition2 = false,
 >     access = condition1 ? condition2 ? "Full pie": "Half pie": 
 >              condition2 ? "Half pie" : "No pie, don't cry" ;
 > console.log(access); // logs "Half pie"
 >```
 
 Use ternary evaluations in free space in order to do different operations.
 >```
 > var stop = false, age = 16;
 > 
 > age > 18 ? location.assign('continue.html') : stop = true;
 >```
 
 Do more than one single operation per case, separating them with a comma.
 >```
 > var stop = false, age = 23;
 >
 > age > 18 ? (
 >      alert('OK, you can go.'),
 >      location.assign('continue.html')
 > ) : (
 >      stop = true,
 >      alert('Sorry, you are much too young!')
 > );
 >```
 
 Do more than one operation during the assignation of a value.
 >```
 > var age = 16;
 >
 > var url = age > 18 ? (
 >      alert('OK, you can go.'), 
 >      // alert returns "undefined", but it will be ignored because
 >      // isn't the last comma-separated value of the parenthesis
 >      'continue.html' // the value to be assigned if age > 18
 > ) : (
 >      alert('You are much too young!'),
 >      alert('Sorry :-('),
 >      // etc. etc.
 >      'stop.html' // the value to be assigned if !(age > 18)
 > );
 >
 > location.assign(url); // "stop.html"
 >```
 
 _In this case, the last comma-separated value of the parenthesis will be the value to be assigned._
 
 
### String Operators

 Concatenation operator (+) concatenates two string values together, returning another string that is the union of the two operand strings.

**_Code Examples_**
>```
> console.log('my ' + 'string'); // console logs the string "my string".
>```

- The shorthand assignment operator += can also be used to concatenate strings.

>```
> var mystring = 'alpha';
> mystring += 'bet'; // evaluates to "alphabet" and assigns this value to mystring.
> ```


### Bitwise Operators

 Bitwise operators treat their operands as a sequence of 32 bits (zeroes and ones),  
 rather than as decimal, hexadecimal, or octal numbers.
 
 For example, the decimal number nine has a binary representation of 1001.  
 Bitwise operators perform their operations on such binary representations,  
 but they return standard JavaScript numerical values.


#### Bitwise Logical Operators
 
 Conceptually, the bitwise logical operators work as follows:
 - The operands are converted to 32-bit integers and expressed by a series of bits (zeroes and ones). Numbers with more than 32 bits get their most significant bits discarded.
 - Each bit in the first operand is paired with the corresponding bit in the second operand: first bit to first bit, second bit to second bit, and so on.
 - The operator is applied to each pair of bits, and the result is constructed bitwise.


##### Bitwise AND ( & )

 Performs the AND operation on each pair of bits. a AND b yields 1 only if both a and b are 1. 
 

##### Bitwise OR ( | )

 Performs the OR operation on each pair of bits. a OR b yields 1 if either a or b is 1.
 

##### Bitwise XOR ( ^ )

 Performs the XOR operation on each pair of bits. a XOR b yields 1 if a and b are different.
 

##### Bitwise NOT ( ~ )

 Performs the NOT operator on each bit. NOT a yields the inverted value (a.k.a. one's complement) of a.
 

#### Bitwise Shift Operators

 The bitwise shift operators take two operands.
 - The first is a quantity to be shifted.
 - and the second specifies the number of bit positions by which the first operand is to be shifted.  

The direction of the shift operation is controlled by the operator used.
 

##### Left Shift Operator ( << )

 This operator shifts the first operand the specified number of bits to the left. 
 Excess bits shifted off to the left are discarded. Zero bits are shifted in from the right.
 
 
##### Sign-propagating Right Shift Operator ( >> )

 This operator shifts the first operand the specified number of bits to the right. 
 Excess bits shifted off to the right are discarded. 
 Copies of the leftmost bit are shifted in from the left. 
 Since the new leftmost bit has the same value as the previous leftmost bit, 
 the sign bit (the leftmost bit) does not change. 
 Hence the name "sign-propagating".
 

##### Zero-fill Right Shift ( >>> )

 This operator shifts the first operand the specified number of bits to the right. 
 Excess bits shifted off to the right are discarded. 
 Zero bits are shifted in from the left. 
 The sign bit becomes 0, so the result is always non-negative.
 
 
#### Signed 32-bit integers
 
 The operands of all bitwise operators are converted to signed 32-bit integers in two's complement format. 
 Two's complement format means that a number's negative counterpart (e.g. 5 vs. -5) is all the number's bits inverted (bitwise NOT of the number, a.k.a. ones' complement of the number) plus one.
 

### Comma Operator

 The comma operator (,) simply evaluates both of its operands and returns the value of the last operand.
 This operator is primarily used inside a `for` loop, to allow multiple variables to be updated each time through the loop.
 
 **_Code Examples_**
 >```
 > for (var i = 0, j = 9; i <= j; i++, j--)
 >     console.log('a[' + i + '][' + j + ']= ' + a[i][j]);
 >```
 
 _If a is a 2-dimensional array with 10 elements on a side, the following code uses the comma operator to update two variables at once._
 _the code prints the values of the diagonal elements in the array_
 
 
### Unary Operators

 A unary operation is an operation with only one operand.
 
#### `delete` Operator

 The `delete` operator removes a property from an object.
 Unlike what common belief suggests, the delete operator has nothing to do with directly freeing memory. (Memory management is done indirectly via breaking references.)
 The `delete` operator removes a given property from an object.
 On successful deletion, it will return `true`,
 else `false` will be returned.
 
 However, it is important to consider the following scenarios:

 - If the property which you are trying to delete does not exist, delete will not have any effect and will return `true`

 - If a property with the same name exists on the object's prototype chain, then, after deletion, the object will use the property from the prototype chain (in other words, delete only has an effect on own properties).
 
 - Any property declared with `var` cannot be deleted from the global scope or from a function's scope.
 
  - As such, delete cannot delete any functions in the global scope (whether this is part from a function definition or a function expression).
 
  - Functions which are part of an object (apart from the global scope) can be deleted with delete.

 - Any property declared with `let` or `const` cannot be deleted from the scope within which they were defined.
 
 - Non-configurable properties cannot be removed. This includes properties of built-in objects like `Math`, `Array`, `Object` and properties that are created as non-configurable with methods like `Object.defineProperty()`.

**_Code Examples_**
>```
> var Employee = {
>   age: 28,
>   name: 'abc',
>   designation: 'developer'
> }
> 
> console.log(delete Employee.name);   // returns true
> console.log(delete Employee.age);    // returns true
> 
> // When trying to delete a property that does 
> // not exist, true is returned 
> console.log(delete Employee.salary); // returns true
>```

**Non-configurable Properties**
 
  When a property is marked as non-configurable, `delete` won't have any effect, and will return `false`.
  In strict mode this will raise a `SyntaxError`.

**_Code Examples_**
>```
> var Employee = {};
> Object.defineProperty(Employee, 'name', {configurable: false});
> 
> console.log(delete Employee.name);  // returns false
>```

`var`, `let` and `const` create non-configurable properties that cannot be deleted with the `delete` operator

**_Code Examples_**
>```
> var nameOther = 'XYZ';
> 
> // We can access this global property using:
> Object.getOwnPropertyDescriptor(window, 'nameOther');  
> 
> // output: Object {value: "XYZ", 
> //                  writable: true, 
> //                  enumerable: true,
> //                  configurable: false}
> 
> // Since "nameOther" is added using with the
> // var keyword, it is marked as "non-configurable"
> 
> delete nameOther;   // return false
>```

In strict mode, this would have raised an exception.


#### `typeof` Operator

 The `typeof` operator returns a string indicating the type of the unevaluated operand.
 
**_Syntax_** 
> `typeof` _`operand`_

**_Parameters_**  
`operand` is an expression representing the object or primitive whose type is to be returned.

The following table summarizes the possible return values of `typeof`.

| Type       | Result         |
| -------    | -------        |
| Undefined  | `"undefined"`  | 
| Null *(See below)*       | `"object"`     |
| Boolean    | `"boolean"`    |
| Number     | `"number"`     |
| String     | `"string"`     |
| Symbol (new in ECMAScript 2015)  | `"symbol"`  |
| Function object (implements [[Call]] in ECMA-262 terms) | `"function"` |
| Any other object | `"object"`     |

**_Code Examples_**
>```
> // Numbers
> typeof 37 === 'number';
> typeof 3.14 === 'number';
> typeof(42) === 'number';
> typeof Math.LN2 === 'number';
> typeof Infinity === 'number';
> typeof NaN === 'number'; // Despite being "Not-A-Number"
> typeof Number(1) === 'number'; // but never use this form!
> 
> // Strings
> typeof '' === 'string';
> typeof 'bla' === 'string';
> typeof '1' === 'string'; // note that a number within a string is still typeof string
> typeof (typeof 1) === 'string'; // typeof always returns a string
> typeof String('abc') === 'string'; // but never use this form!
> 
> // Booleans
> typeof true === 'boolean';
> typeof false === 'boolean';
> typeof Boolean(true) === 'boolean'; // but never use this form!
> 
> // Symbols
> typeof Symbol() === 'symbol'
> typeof Symbol('foo') === 'symbol'
> typeof Symbol.iterator === 'symbol'
> 
> // Undefined
> typeof undefined === 'undefined';
> typeof declaredButUndefinedVariable === 'undefined';
> typeof undeclaredVariable === 'undefined'; 
>
> // Objects
> typeof {a: 1} === 'object';
>
> // use Array.isArray or Object.prototype.toString.call
> // to differentiate regular objects from arrays
> typeof [1, 2, 4] === 'object';
>
> typeof new Date() === 'object';
> 
> // The following is confusing. Don't use!
> typeof new Boolean(true) === 'object'; 
> typeof new Number(1) === 'object'; 
> typeof new String('abc') === 'object';
>
> // Functions
> typeof function() {} === 'function';
> typeof class C {} === 'function';
> typeof Math.sin === 'function';
>```

**_Notes_**

**`null`**
>```
> // This stands since the beginning of JavaScript
> typeof null === 'object';
>```

 In the first implementation of JavaScript, JavaScript values were represented as a type tag and a value.  
 The type tag for objects was 0. null was represented as the NULL pointer (0x00 in most platforms).  
 Consequently, null had 0 as type tag, hence the bogus typeof return value.  
 A fix was proposed for **ECMAScript** (via an opt-in), but was rejected. It would have resulted in `typeof` _`null === 'null'`_
 
**Regular expressions**  
 Callable regular expressions were a non-standard addition in some browsers.
>```
> typeof /s/ === 'function'; // Chrome 1-12 Non-conform to ECMAScript 5.1
> typeof /s/ === 'object';   // Firefox 5+  Conform to ECMAScript 5.1
>```

**Exceptions**  
All current browsers expose a non-standard host object `document.all` with type Undefined.
>```
> typeof document.all === 'undefined'
>```

 Although the specification allows custom type tags for non-standard exotic objects, it requires those type tags to be different from the predefined ones.  
 The case of `document.all` having type tag `'undefined'` must be classified as an exceptional violation of the rules.


#### `void` Operator

 The `void` operator evaluates the given expression and then returns `undefined`.

**_Syntax_** 
> `void` _`expression`_

 This operator allows inserting expressions that produce side effects into places where an expression that evaluates to `undefined` is desired.

 The `void` operator is often used merely to obtain the undefined primitive value, usually using "`void(0)`" (which is equivalent to "`void 0`").  
 In these cases, the global variable `undefined` can be used instead (assuming it has not been assigned to a non-default value).

**Immediately Invoked Function Expressions**

 When using an _immediately-invoked function expression_, `void` can be used to force the `function` keyword to be treated as an expression instead of a declaration.

**_Code Examples_**
>```
> void function iife() {
>     var bar = function () {};
>     var baz = function () {};
>     var foo = function () {
>         bar();
>         baz();
>      };
>     var biz = function () {};
> 
>     foo();
>     biz();
> }();
>```

**JavaScript URIs**

 When a browser follows a javascript: URI, it evaluates the code in the URI and then replaces the contents of the page with the returned value, unless the returned value is undefined. The void operator can be used to return undefined. For example:

**_Code Examples_**
>```
> <a href="javascript:void(0);">
>   Click here to do nothing
> </a>
> 
> <a href="javascript:void(document.body.style.backgroundColor='green');">
>   Click here for green background
> </a>
>```

**_Note_**
However, that the `javascript:` pseudo protocol is discouraged over other alternatives, such as unobtrusive event handlers.


### Relational Operators
 
#### `in` Operator

 The `in` operator returns true if the specified property is in the specified object.
 
**_Syntax_** 
> _`prop`_ `in` _`objectName`_

**_Parameter_**  
__prop__  
 > A string or symbol representing a property name or array index (non-symbols will be coerced to strings).

__objectName__  
 > Name of an object.

**_Code Examples_**
>```
// Arrays
> var trees = ['redwood', 'bay', 'cedar', 'oak', 'maple'];
> 0 in trees        // returns true
> 3 in trees        // returns true
> 6 in trees        // returns false
> 'bay' in trees    // returns false (you must specify the 
>                   // index number, not the value at that index)
> 'length' in trees // returns true (length is an Array property)
> Symbol.iterator in trees // returns true (arrays are iterable, works only in ES2015+)
>
> // Predefined objects
> 'PI' in Math          // returns true
>
> // Custom objects
> var mycar = {make: 'Honda', model: 'Accord', year: 1998};
> 'make' in mycar  // returns true
> 'model' in mycar // returns true
> 
>```

 You must specify an object on the right side of the in operator. For example, you can specify a string created with the String constructor, but you cannot specify a string literal.

>```
> var color1 = new String('green');
> 'length' in color1 // returns true
>
> var color2 = 'coral';
> // generates an error (color2 is not a String object)
> 'length' in color2
>```

Using `in` with `deleted` or `undefined` properties

 If you delete a property with the `delete` operator, the in operator returns `false` for that property.

>```
> var mycar = {make: 'Honda', model: 'Accord', year: 1998};
> delete mycar.make;
> 'make' in mycar;  // returns false
>
> var trees = new Array('redwood', 'bay', 'cedar', 'oak', 'maple');
> delete trees[3];
> 3 in trees; // returns false
>```

 If you set a property to `undefined` but do not delete it, the in operator returns true for that property.

>```
> var mycar = {make: 'Honda', model: 'Accord', year: 1998};
> mycar.make = undefined;
> 'make' in mycar;  // returns true
>
> var trees = new Array('redwood', 'bay', 'cedar', 'oak', 'maple');
> trees[3] = undefined;
> 3 in trees; // returns true
>```

Inherited properties

The in operator returns `true` for properties in the prototype chain.

>```
> 'toString' in {}; // returns true
>```


#### `instanceof` Operator

 The `instanceof` operator tests whether an object in its prototype chain has the prototype property of a constructor.

**_Syntax_** 
> _`object`_ `instanceof` _`constructor`_

**_Parameter_** 
__object__
> The object to test.

__constructor__
> Function to test against

The `instanceof` operator tests presence of `constructor.prototype` in `object`'s prototype chain.

**_Code Examples_**
>```
> // defining constructors
> function C() {}
> function D() {}
> 
> var o = new C();
> 
> // true, because: Object.getPrototypeOf(o) === C.prototype
> o instanceof C;
> 
> // false, because D.prototype is nowhere in o's prototype chain
> o instanceof D;
> 
> o instanceof Object; // true, because:
> C.prototype instanceof Object // true
> 
> C.prototype = {};
> var o2 = new C();
> 
> o2 instanceof C; // true
>
> // false, because C.prototype is nowhere in
> // o's prototype chain anymore
> o instanceof C; 
> 
> D.prototype = new C(); // add C to [[Prototype]] linkage of D
> var o3 = new D();
> o3 instanceof D; // true
> o3 instanceof C; // true since C.prototype is now in o3's prototype chain
>```

---

## Expressions
 
 An `expression` is any valid unit of code that resolves to a value.  
 Every syntactically valid expression resolves to some value but conceptually, there are two types of expressions
 1. with side effects (for example: those that assign value to a variable) 
 2. and those that in some sense evaluates and therefore resolves to value.
 
The expression x = 7 is an example of the first type.  
This expression uses the `=` operator to assign the value seven to the variable x.  
The expression itself evaluates to seven.

The code 3 + 4 is an example of the second expression type.
This expression uses the + operator to add three and four together without assigning the result, seven, to a variable.

__JavaScript has the following expression categories:__
- **Arithmetic:** evaluates to a number, for example 3.14159. (Generally uses arithmetic operators.)
- **String:** evaluates to a character string, for example, "Fred" or "234". (Generally uses string operators.)
- **Logical:** evaluates to true or false. (Often involves logical operators.)
- **Primary Expressions:** Basic keywords and general expressions in JavaScript.  

 `this` keyword (For example)  

  Use the `this` keyword to refer to the current object.  
  In general, `this` refers to the calling object in a method.  
  Use `this` either with the dot or the bracket notation.
  
  >```
  > this['propertyName']
  > this.propertyName
  >```
  
  Grouping operator  
  The grouping operator ( ) controls the precedence of evaluation in expressions.  
  For example, you can override multiplication and division first, then addition and subtraction to evaluate addition first.
  
  >```
  > var a = 1;
  > var b = 2;
  > var c = 3;
  > 
  > // default precedence
  > a + b * c     // 7
  > // evaluated by default like this
  > a + (b * c)   // 7
  > 
  > // now overriding precedence 
  > // addition before multiplication   
  > (a + b) * c   // 9
  >   
  > // which is equivalent to
  > a * c + b * c // 9
  >```

  Comprehensions  
  Comprehensions are an experimental JavaScript feature, targeted to be included in a future ECMAScript version. There are two versions of comprehensions
  > `[for (x of y) x]` Array comprehensions.  
  > `(for (x of y) y)` Generator comprehensions.
  
  Comprehensions exist in many programming languages and allow you to quickly assemble a new array based on an existing one
  

- **Left-hand-side Expressions:** Left values are the destination of an assignment.

  **`new` operator**  
  You can use the `new` operator to create an instance of a user-defined object type or of one of the built-in object types.
  
  > `var objectName = new objectType([param1, param2, ..., paramN]);`

  **`super` keyword**  
  The `super` keyword is used to call functions on an object's parent. It is useful with classes to call the parent constructor.
  
  > `super([arguments]); // calls the parent constructor.`
  > `super.functionOnParent([arguments]);`

  **`Spread` operator** 
  The `spread` operator allows an expression to be expanded in places where multiple arguments (for function calls) or multiple elements (for array literals) are expected.
  
  > `var parts = ['shoulder', 'knees'];`  
  > `var lyrics = ['head', ...parts, 'and', 'toes'];`
  
  Similarly, the spread operator works with function calls:
  
  >```
  > function f(x, y, z) { }
  > var args = [0, 1, 2];
  > f(...args);
  >```
  

### Object Initializer

 Objects can be initialized using new Object(), Object.create(), or using the literal notation (initializer notation). An object initializer is a comma-delimited list of zero or more pairs of property names and associated values of an object, enclosed in curly braces ({}).
 
**_Syntax_** 
>```
> var o = {};
> var o = {a: 'foo', b: 42, c: {}};
>
> var a = 'foo', b = 42, c = {};
> var o = {a: a, b: b, c: c};
> 
> var o = {
>   property: function ([parameters]) {},
>   get property() {}
>   set property(value) {}
> };
>```
 
**New notations in ECMAScript 2015**


>```
> // Shorthand property names (ES2015)
> var a = 'foo', b = 42, c = {};
> var o = {a, b, c};
> 
> // Shorthand method names (ES2015)
> var o = {
>   property([parameters]) {}
> };
> 
> // Computed property names (ES2015)
> var prop = 'foo';
> var o = {
>   [prop]: 'hey',
>   ['b' + 'ar']: 'there'
> };
>```

 An object initializer is an expression that describes the initialization of an `Object`.  
 Objects consist of `properties`, which are used to describe an object.  
 Values of object properties can either contain primitive data types or other objects.

## Creating Objects

 An empty object with no properties can be created like this
> `var object = {};`

 However, the advantage of the _literal_ or _initializer_ notation is, that you are able to quickly create objects with properties inside the curly braces.  
 You simply notate a list of `key: value` pairs delimited by comma.  
 The following code creates an object with three properties and the keys are __"foo"__, __"age"__ and __"baz"__.  The values of these keys are a string __"bar"__, a number 42 and the third property has another object as its value.

>```
> var object = {
>   foo: 'bar',
>   age: 42,
>   baz: {myProp: 12}
> }
>```

#### Accessing Properties

 Once you have created an object, you might want to read or change them. Object properties can be accessed by using the dot notation or the bracket notation.  
 See **### Property Accessors** for detailed information.

>```
> object.foo; // "bar"
> object['age']; // 42
>
> object.foo = 'baz';
>```

#### Property definitions

 We have already learned how to notate properties using the initializer syntax.
 Oftentimes, there are variables in your code that you would like to put into an object.
 You will see code like this:

>```
> var a = 'foo', 
>    b = 42,
>    c = {};
>
> var o = { 
>   a: a,
>   b: b,
>   c: c
> };
>```

With ECMAScript 2015, there is a shorter notation available to achieve the same:

>```
> var a = 'foo', 
>    b = 42, 
>    c = {};
>
> // Shorthand property names (ES2015)
> var o = {a, b, c};
>
> // In other words,
> console.log((o.a === {a}.a)); // true
>```


#### Method definitions

 A property of an object can also refer to a `function` or a `getter` or `setter` method.
 
>```
> var o = {
>   property: function ([parameters]) {},
>   get property() {},
>   set property(value) {}
>```

 In ECMAScript 2015, a shorthand notation is available, so that the keyword "function" is no longer necessary.

>```
> // Shorthand method names (ES2015)
> var o = {
>   property([parameters]) {},
>   *generator() {}
> };
>```

 In ECMAScript 2015 There is a way to concisely define properties whose values are generator functions:
 
>```
> var o = {
>   *generator() {
>       ...........
>   }
> };
>```

 Which is equivalent to this ES5-like notation (but note that ECMAScript 5 has no generators):
 
>```
> var o = {
>   generator: function* () {
>     ...........
>   }
> };
>```

#### Computed Property Names

 Starting with ECMAScript 2015, the object initializer syntax also supports computed property names.  That allows you to put an expression in brackets [], that will be computed as the property name. 
 This is symmetrical to the bracket notation of the property accessor syntax, which you might have used to read and set properties already.  
 Now you can use the same syntax in object literals, too:
 
>```
> // Computed property names (ES2015)
> var i = 0;
> var a = {
>   ['foo' + ++i]: i,
>   ['foo' + ++i]: i,
>   ['foo' + ++i]: i
> };
>
> console.log(a.foo1); // 1
> console.log(a.foo2); // 2
> console.log(a.foo3); // 3
>
> var param = 'size';
> var config = {
>   [param]: 12,
>   ['mobile' + param.charAt(0).toUpperCase() + param.slice(1)]: 4
> };
> 
> console.log(config); // {size: 12, mobileSize: 4}
>```


#### Spread Properties

 The Rest/Spread Properties for ECMAScript proposal (stage 3) adds spread properties to object literals. It copies own enumerable properties from a provided object onto a new object.
 
 Shallow-cloning (excluding prototype) or merging objects is now possible using a shorter syntax than `Object.assign()`.
 
>```
> var obj1 = { foo: 'bar', x: 42 };
> var obj2 = { foo: 'baz', y: 13 };
> 
> var clonedObj = { ...obj1 };
> // Object { foo: "bar", x: 42 }
>
> var mergedObj = { ...obj1, ...obj2 };
> // Object { foo: "baz", x: 42, y: 13 }
>```

**Note** that `Object.assign()` triggers setters whereas the spread operator doesn't.


#### Prototype Mutation

 A property definition of the form __proto__: value or "__proto__": value does not create a property with the name __proto__. 
 
 Instead, if the provided value is an object or null, it changes the [[Prototype]] of the created object to that value.
 (If the value is not an object or null, the object is not changed.)
 
 >```
 > var obj1 = {};
 > assert(Object.getPrototypeOf(obj1) === Object.prototype);
 > 
 > var obj2 = {__proto__: null};
 > assert(Object.getPrototypeOf(obj2) === null);
 >
 > var protoObj = {};
 > var obj3 = {'__proto__': protoObj};
 > assert(Object.getPrototypeOf(obj3) === protoObj);
 >
 > var obj4 = {__proto__: 'not an object or null'};
 > assert(Object.getPrototypeOf(obj4) === Object.prototype);
 > assert(!obj4.hasOwnProperty('__proto__'));
 >```
 
 Only a single prototype mutation is permitted in an object literal: multiple prototype mutations are a syntax error.
 
 Property definitions that do not use "colon" notation are not prototype mutations: they are property definitions that behave identically to similar definitions using any other name.
 
 >```
 > var __proto__ = 'variable';
 > 
 > var obj1 = {__proto__};
 > assert(Object.getPrototypeOf(obj1) === Object.prototype);
 > assert(obj1.hasOwnProperty('__proto__'));
 > assert(obj1.__proto__ === 'variable');
 > 
 > var obj2 = {__proto__() { return 'hello'; }};
 > assert(obj2.__proto__() === 'hello');
 > 
 > var obj3 = {['__prot' + 'o__']: 17};
 > assert(obj3.__proto__ === 17);
 >```
 
#### Object Literal Notation vs JSON

 The object literal notation is not the same as the JavaScript Object Notation (JSON).   
 Although they look similar, there are differences between them:
 
 - JSON permits only property definition using `"property": value` syntax.  The property name must be double-quoted, and the definition cannot be a shorthand.
 - In JSON the values can only be strings, numbers, arrays, `true`, `false`, `null`, or another (JSON) object.
 - A function value (see "Methods" above) can not be assigned to a value in JSON.
 - Objects like `Date` will be a string after `JSON.parse()`.
 - `JSON.parse()` will reject computed property names and an error will be thrown.
 

### Property Accessors

 Property accessors provide access to an object's properties by using the dot notation or the bracket notation.
 
**_Syntax_** 
>```
> object.property
> object['property']
>```
 
One can think of an object as an *associative array* (a.k.a. map, dictionary, hash, lookup table). 
The keys in this array are the names of the object's properties.
It's typical when speaking of an object's properties to make a distinction between properties and methods.  
However, the property/method distinction is little more than a convention.   
A method is simply a property that can be called, for example if it has a reference to a Function instance as its value.

There are two ways to access properties: dot notation and bracket notation.

#### Dot Notation

>```
> get = object.property;
> object.property = set;
>```

In this code, property must be a valid JavaScript identifier, i.e. a sequence of alphanumerical characters, also including the underscore ("_") and dollar sign ("$"), that cannot start with a number.  
For example, object.$1 is valid, while object.1 is not.

>```
> document.createElement('pre');
>```

Here, the method named "createElement" is retrieved from document and is called.

If you use a method for a numeric literal and the numeric literal has no exponent and no decimal point, leave white-space(s) before the dot that precedes the method call to prevent the dot from being interpreted as a decimal point.

>```
> 77 .toExponential();
> // or
> 77
> .toExponential();
> // or
> (77).toExponential();
> // or
> 77..toExponential();
> // or
> 77.0.toExponential();
> // because 77. === 77.0, no ambiguity
>```

#### Bracket Notation

>```
> get = object[property_name];
> object[property_name] = set;
>```

property_name is a string. The string does not have to be a valid identifier; it can have any value, e.g. "1foo", "!bar!", or even " " (a space).

>```
> document['createElement']('pre');
>```

This does the exact same thing as the previous example.

A space before bracket notation is allowed.

>```
> document ['createElement']('pre');
>```

#### Property Names

Property names must be strings.  
This means that non-string objects cannot be used as keys in the object.  
Any non-string object, including a number, is typecasted into a string via the `toString` method.

>```
> var object = {};
> object['1'] = 'value';
> console.log(object[1]);
>```

This outputs "value", since 1 is type-casted into '1'.

>```
> var foo = {unique_prop: 1}, bar = {unique_prop: 2}, object = {};
> object[foo] = 'value';
> console.log(object[bar]);
>```

This also outputs "value", since both foo and bar are converted to the same string.

#### Method Binding

A method is not bound to the object that it is a method of. 
Specifically, `this` is not fixed in a method,  i.e., `this` does not necessarily refer to an object containing the method. `this` is instead "passed" by the function call.

#### Note on `eval`

JavaScript novices often make the mistake of using eval where the bracket notation can be used instead.  
For example, the following syntax is often seen in many scripts.

>```
> x = eval('document.forms.form_name.elements.' + strFormControl + '.value');
>```

`eval` is slow and should be avoided whenever possible.  
Also, `strFormControl` would have to hold an identifier, which is not required for names and IDs of form controls.
It is better to use bracket notation instead:

>```
> x = document.forms['form_name'].elements[strFormControl].value;
>```


### Operator Precedence

 Operator precedence determines the order in which operators are evaluated.  
 Operators with higher precedence are evaluated first.
 
 A common example:
 >```
 > 3 + 4 * 5 // returns 23
 >```
 
 The multiplication operator ("*") has higher precedence than the addition operator ("+") and thus will be evaluated first.
 
#### Associativity

 Associativity determines the order in which operators of the same precedence are processed.
 For example, consider an expression:
 
 >```
 > a OP b OP c
 >```
 
 Left-associativity (left-to-right) means that it is processed as (a OP b) OP c, while right-associativity (right-to-left) means it is interpreted as a OP (b OP c).  
 Assignment operators are right-associative, so you can write.
 
 >```
 > a = b = 5;
 >```
 
 with the expected result that a and b get the value 5.  
 This is because the assignment operator returns the value that it assigned.
 First, b is set to 5. Then the a is also set to 5, the return value of b = 5, aka right operand of the assignment.
 
#### Table

 The following table is ordered from highest (20) to lowest (0) precedence.

| Precedence | Operator type               | Associativity | Individual operators |
|   :---:    | --------------------------- | ------------- |      :---------:     |
| 20         | Grouping                    | n/a           | ( … )                |
| 19         | Member Access               | left-to-right | … . …                |
|            | Computed Member Access      | left-to-right | … [ … ]              |
|            | new (with argument list)    | n/a           | new … ( … )          |
|            | Function Call               | left-to-right | … ( … )              |
| 18         | new (without argument list) | right-to-left | new …                |
| 17         | Postfix Increment           | right-to-left | … ++                 |
|            | Postfix Decrement           | right-to-left | … --                 |
| 16         | Logical NOT                 | right-to-left | ! …                  |
|            | Bitwise NOT                 | right-to-left | ~ …                  |
|            | Unary Plus                  | right-to-left | + …                  |
|            | Unary Negation              | right-to-left | - …                  |
|            | Prefix Increment            | right-to-left | ++ …                 |
|            | Prefix Decrement            | right-to-left | -- …                 |
|            | typeof                      | right-to-left | typeof …             |
|            | void                        | right-to-left | void …               |
|            | delete                      | right-to-left | delete …             |
| 15         | Exponentiation              | right-to-left | … ** …               |
| 14         | Multiplication              | left-to-right | … * …                |
|            | Division                    | left-to-right | … / …                |
|            | Remainder                   | left-to-right | … % …                |
| 13         | Addition                    | left-to-right | … + …                |
|            | Subtraction                 | left-to-right | … - …                |
| 12	     | Bitwise Left Shift	       | left-to-right | … << …               |
|            | Bitwise Right Shift	       | left-to-right | … >> …               |
|            | Bitwise Unsigned Right Shift| left-to-right | … >>> …              |
| 11	     | Less Than	               | left-to-right | … < …                |
|            | Less Than Or Equal	       | left-to-right | … <= …               |
|            | Greater Than	               | left-to-right | … > …                |
|            | Greater Than Or Equal	   | left-to-right | … >= …               | 
|            | in	                       | left-to-right | … in …               |
|            | instanceof	               | left-to-right | … instanceof …       |
| 10	     | Equality	                   | left-to-right | … == …               |
|            | Inequality	               | left-to-right | … != …               | 
|            | Strict Equality	           | left-to-right | … === …              |
|            | Strict Inequality	       | left-to-right | … !== …              | 
| 9	         | Bitwise AND	               | left-to-right | … & …                |
| 8	         | Bitwise XOR	               | left-to-right | … ^ …                |
| 7	         | Bitwise OR	               | left-to-right | … &#124; …           | 
| 6	         | Logical AND	               | left-to-right | … && …               |
| 5	         | Logical OR	               | left-to-right | … &#124;&#124; …     |
| 4	         | Conditional	               | right-to-left | … ? … : …            | 
| 3	         | Assignment	               | right-to-left | … = …                |
|            |                             |               | … += …               |
|            |                             |               | … -= …               |
|            |                             |               | … **= …              |
|            |                             |               | … *= …               |
|            |                             |               | … /= …               |
|            |                             |               | … %= …               |
|            |                             |               | … <<= …              |
|            |                             |               | … >>= …              |
|            |                             |               | … >>>= …             |
|            |                             |               | … &= …               |
|            |                             |               | … ^= …               |
|            |                             |               | … |= …               |
| 2	         | yield	                   | right-to-left | yield …              |
|            | yield*	                   | right-to-left | yield* …             |
| 1	         | Spread                      | n/a           | ... …                |
| 0	         | Comma / Sequence	           | left-to-right | … , …                |


### Expression Closures

 Expression closures are a shorthand function syntax for writing simple functions.
 This addition is nothing more than a shorthand for writing simple functions, giving the language something similar to a typical Lambda notation.
 
**_Syntax_** 
>```
> function [name]([param1[, param2[, ..., paramN]]])
>   expression
>```

JavaScript 1.7 and older:
> `function(x) { return x * x; }`

JavaScript 1.8:
> `function(x) x * x`

This syntax allows you to leave off the braces and 'return' statement - making them implicit. There is no added benefit to writing code in this manner, other than having it be syntactically shorter.


**_Parameters_** 
- **name**  
  The function name. Can be omitted, in which case the function is `anonymous`.  
  The name is only local to the function body.
  
  
- **paramN**  
  The name of an argument to be passed to the function.  
   A function can have up to 255 arguments.
  
  
- **expression**  
  The expression which comprise the body of the function.
  
  
**_Examples_** 

- A shorthand for binding event listeners:
    > `document.addEventListener('click', function() false, true);`


- Using this notation with some of the array functions from JavaScript 1.6:
    > `elems.some(function(elem) elem.type == 'text');`
    

### Destructuring Assignment
 
 The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.
 
 **_Syntax_**
 >``` 
 > var a, b, rest;
 > [a, b] = [10, 20];
 > console.log(a); // 10
 > console.log(b); // 20
 >
 > [a, b, ...rest] = [10, 20, 30, 40, 50];
 > console.log(a); // 10
 > console.log(b); // 20
 > console.log(rest); // [30, 40, 50]
 >
 > ({a, b} = {a: 10, b: 20});
 > console.log(a); // 10
 > console.log(b); // 20
 >
 > // Stage 3 proposal
 > ({a, b, ...rest} = {a: 10, b: 20, c: 30, d: 40});
 >```
 
 The object and array literal expressions provide an easy way to create `ad hoc` packages of data.
 
 > `var x = [1, 2, 3, 4, 5];`

 The destructuring assignment uses similar syntax.
 but on the left-hand side of the assignment to define what values to unpack from the sourced variable.
 
 >```
 > var x = [1, 2, 3, 4, 5];
 > var [y, z] = x;
 > console.log(y); // 1
 > console.log(z); // 2
 >```

 This capability is similar to features present in languages such as Perl and Python.


#### Array Destructuring

**_Basic Variable Assignment_**
>```
> var foo = ['one', 'two', 'three'];
>
> var [one, two, three] = foo;
> console.log(one); // "one"
> console.log(two); // "two"
> console.log(three); // "three"
>```


**_Assignment Separate from Declaration_**

 A variable can be assigned its value via destructuring separate from the variable's declaration.

>```
> var a, b;
> 
> [a, b] = [1, 2];
> console.log(a); // 1
> console.log(b); // 2
>```

**_Default Values_**

 A variable can be assigned a default, in the case that the value unpacked from the array is `undefined`.
 
 >```
 > var a, b;
 >
 > [a=5, b=7] = [1];
 > console.log(a); // 1
 > console.log(b); // 7
 >```
 
**_Swapping Variables_**

 Two variables values can be swapped in one destructuring expression.
 Without destructuring assignment, swapping two values requires a temporary variable (or, in some low-level languages, the XOR-swap trick).

 >```
 > var a = 1;
 > var b = 3;
 >
 > [a, b] = [b, a];
 > console.log(a); // 3
 > console.log(b); // 1
 >```

**_Parsing an array returned from a function_**

 It's always been possible to return an array from a function.
 Destructuring can make working with an array return value more concise.

 In this example, 
 `f()` returns the values `[1, 2]` as its output, which can be parsed in a single line with destructuring.
 
 >```
 > function f() {
 >  return [1, 2];
 > }
 >
 > var a, b; 
 > [a, b] = f(); 
 > console.log(a); // 1
 > console.log(b); // 2
 >```
 
**_Ignoring some returned values_** 

 You can ignore return values that you're not interested in:
 
>```
> function f() {
>   return [1, 2, 3];
> } 
>
> var [a, , b] = f();
> console.log(a); // 1
> console.log(b); // 3
>```

 You can also ignore all returned values:
 
> `[,,] = f();`


**_Assigning the rest of an array to a variable_**

 When destructuring an array, you can unpack and assign the remaining part of it to a variable using the rest pattern:
 
>```
> var [a, ...b] = [1, 2, 3];
> console.log(a); // 1
> console.log(b); // [2, 3]
>```

 Note that a SyntaxError will be thrown if a trailing comma is used on the left-hand side with a rest element:

>```
> var [a, ...b,] = [1, 2, 3];
> // SyntaxError: rest element may not have a trailing comma
>```

**_Unpacking values from a regular expression match_**
 
 When the regular expression `exec()` method finds a match, it returns an array containing first the entire matched portion of the string and then the portions of the string that matched each parenthesized group in the regular expression.
 Destructuring assignment allows you to unpack the parts out of this array easily, ignoring the full match if it is not needed.
 
>```
> var url = 'https://developer.mozilla.org/en-US/Web/JavaScript';
> 
> var parsedURL = /^(\w+)\:\/\/([^\/]+)\/(.*)$/.exec(url);
> console.log(parsedURL); // ["https://developer.mozilla.org/en-US/Web/JavaScript", "https", "developer.mozilla.org", "en-US/Web/JavaScript"]
>
> var [, protocol, fullhost, fullpath] = parsedURL;
>
> console.log(protocol); // "https"
>```


#### Object Destructuring

**_Basic Assignment_**

>```
> var o = {p: 42, q: true};
> var {p, q} = o;
>
> console.log(p); // 42
> console.log(q); // true
>```

**_Assignment without declaration_**

 A variable can be assigned its value with destructuring separate from its declaration.

>```
> var a, b;
>
> ({a, b} = {a: 1, b: 2});
>```

**_Assigning to new variable names_**

 A property can be unpacked from an object and assigned to a variable with a different name than the object property.

>```
> var o = {p: 42, q: true};
> var {p: foo, q: bar} = o;
>
> console.log(foo); // 42 
> console.log(bar); // true
>```

**_Default values_**

 A variable can be assigned a default, in the case that the value unpacked from the object is `undefined`.
 
>```
> var {a = 10, b = 5} = {a: 3};
>
> console.log(a); // 3
> console.log(b); // 5
>```

**_Setting a function parameter's default value_**
*ES5 version*

>```
> function drawES5Chart(options) {
>  options = options === undefined ? {} : options;
>  var size = options.size === undefined ? 'big' : options.size;
>  var cords = options.cords === undefined ? {x: 0, y: 0} : options.cords;
>  var radius = options.radius === undefined ? 25 : options.radius;
>  console.log(size, cords, radius);
>  // now finally do some chart drawing
> }
> 
> drawES5Chart({
>   cords: {x: 18, y: 30},
>   radius: 30
> });
>```

*ES2015 version*
>```
> function drawES2015Chart({size = 'big', cords = {x: 0, y: 0}, radius = 25} = {}) {
>   console.log(size, cords, radius);
>   // do some chart drawing
> }
> drawES2015Chart({
>   cords: {x: 18, y: 30},
>   radius: 30
> });
>```

**_Nested object and array destructuring_**

>```
> var metadata = {
>     title: 'Scratchpad',
>     translations: [
>        {
>         locale: 'de',
>         localization_tags: [],
>         last_edit: '2014-04-14T08:43:37',
>         url: '/de/docs/Tools/Scratchpad',
>         title: 'JavaScript-Umgebung'
>        }
>     ],
>     url: '/en-US/docs/Tools/Scratchpad'
> };
>
> var {title: englishTitle, translations: [{title: localeTitle}]} = metadata;
>
> console.log(englishTitle); // "Scratchpad"
> console.log(localeTitle);  // "JavaScript-Umgebung"
>```

**_For of iteration and destructuring_**

>```
> var people = [
>   {
>     name: 'Mike Smith',
>     family: {
>       mother: 'Jane Smith',
>       father: 'Harry Smith',
>       sister: 'Samantha Smith'
>     },
>     age: 35
>   },
>   {
>     name: 'Tom Jones',
>     family: {
>       mother: 'Norah Jones',
>       father: 'Richard Jones',
>       brother: 'Howard Jones'
>     },
>     age: 25
>   }
> ];
> 
> for (var {name: n, family: {father: f}} of people) {
>   console.log('Name: ' + n + ', Father: ' + f);
> }
> 
> // "Name: Mike Smith, Father: Harry Smith"
> // "Name: Tom Jones, Father: Richard Jones"
>```

**_Unpacking fields from objects passed as function parameter_**

>```
> function userId({id}) {
>   return id;
> }
>
> function whois({displayName, fullName: {firstName: name}}) {
>   console.log(displayName + ' is ' + name);
> }
>
> var user = { 
>   id: 42, 
>   displayName: 'jdoe',
>   fullName: { 
>       firstName: 'John',
>       lastName: 'Doe'
>   }
> };
>
> console.log('userId: ' + userId(user)); // "userId: 42"
> whois(user); // "jdoe is John"
>```

This unpacks the `id`, `displayName` and `firstName` from the user object and prints them.

**_Computed object property names and destructuring_**

 Computed property names, like on object literals, can be used with destructuring.

>```
> let key = 'z';
> let {[key]: foo} = {z: 'bar'};
> 
> console.log(foo); // "bar"
>```

**_Rest in Object Destructuring_**

 The Rest/Spread Properties for ECMAScript proposal (stage 3) adds the rest syntax to destructuring.
 Rest properties collect the remaining own enumerable property keys that are not already picked off by the destructuring pattern.
 
>```
> let {a, b, ...rest} = {a: 10, b: 20, c: 30, d: 40}
> a; // 10 
> b; // 20 
> rest; // { c: 30, d: 40 }
>```

**_Invalid JavaScript identifier as a property name_**

 Destructuring can be used with property names that are not valid JavaScript identifiers by providing an alternative identifer that is valid.

>```
> const foo = { 'fizz-buzz': true };
> const { 'fizz-buzz': fizzBuzz } = foo;
> 
> console.log(fizzBuzz); // "true"
>```


### Spread Syntax

 Spread syntax allows an iterable such as an array expression to be expanded in places where zero or more arguments (for function calls) or elements (for array literals) are expected, or an object expression to be expanded in places where zero or more key-value pairs (for object literals) are expected.
 

**_Syntax_**

**For function calls:**
>```
> myFunction(...iterableObj);
>```

**For array literals:**
>```
> [...iterableObj, 4, 5, 6];
>```

**For object literals (new in ECMAScript; stage 3 draft):**
>```
> let objClone = { ...obj };
>```

**_Examples_**
**Spread in function calls**

*Replace apply*
It is common to use `Function.prototype.apply` in cases where you want to use the elements of an array as arguments to a function.

>```
> function myFunction(x, y, z) { }
> var args = [0, 1, 2];
> myFunction.apply(null, args);
>```

With spread syntax the above can be written as:

>```
> function myFunction(x, y, z) { }
> var args = [0, 1, 2];
> myFunction(...args);
>```

Any argument in the argument list can use spread syntax and it can be used multiple times.

>```
> function myFunction(v, w, x, y, z) { }
> var args = [0, 1];
> myFunction(-1, ...args, 2, ...[3]);
>```


**Apply for new**

 When calling a constructor with `new`, it's not possible to directly use an array and apply (apply does a [[Call]] and not a [[Construct]]). 
 However, an array can be easily used with new thanks to spread syntax:
 
>```
> var dateFields = [1970, 0, 1];  // 1 Jan 1970
> var d = new Date(...dateFields);
>```

To use new with an array of parameters without spread syntax

>```
> function applyAndNew(constructor, args) {
>    function partial () {
>       return constructor.apply(this, args);
>    };
>    if (typeof constructor.prototype === "object") {
>       partial.prototype = Object.create(constructor.prototype);
>    }
>    return partial;
> }
>
> function myConstructor () {
>    console.log("arguments.length: " + arguments.length);
>    console.log(arguments);
>    this.prop1="val1";
>    this.prop2="val2";
> };
> 
> var myArguments = ["hi", "how", "are", "you", "mr", null];
> var myConstructorWithArguments = applyAndNew(myConstructor, myArguments);
>
> console.log(new myConstructorWithArguments);
> // (internal log of myConstructor):           arguments.length: 6
> // (internal log of myConstructor):           ["hi", "how", "are", "you", "mr", null]
> // (log of "new myConstructorWithArguments"): {prop1: "val1", prop2: "val2"}
>```


Spread in array literals

A more powerful array literal

 Without spread syntax, to create a new array using an existing array as one part of it, the array literal syntax is no longer sufficient and imperative code must be used instead using a combination of push, splice, concat, etc.
 With spread syntax this becomes much more succinct:

>```
> var parts = ['shoulders', 'knees']; 
>```


### Function Expression


### Function* Expression


### Legacy Generator Function Expression


### Async Function Expression


### Class Expression


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

