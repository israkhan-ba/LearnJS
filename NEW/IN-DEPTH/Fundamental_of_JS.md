# Fundamental of JavaScript

In this page, it will explain shortly about all of the JavaScript fundamental elements and concepts which will set a quick overview for the very basic of JavaScript

And it will be recommended to re-read this page frequently as it could help you understand and get clarify with JavaScript quickly.

So its very intention is to make you less confuse.


## Syntax

Syntax is a set of rules that defined how a program are constructed.  
It is how to write a program that work in a programming language, if you write a wrong syntax your your codes will not work.

Programming is **instructions** that listing well so a computer can be executed, and each program instructions are generally called **statements**, So basically we can call any program is a set and sequence of statements working together.

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


### Template Literals
Template literals are string literals allowing embedded expressions.
You can use multi-line strings and string interpolation features with them.
They were called "template strings" in prior editions of the ES2015 specification.


**_Syntax_**

>```
> `string text`
> 
> `string text line 1
>  string text line 2`
> 
> `string text ${expression} string text`
> 
> tag `string text ${expression} string text`
>```


Template literals are enclosed by the back-tick (` `) (grave accent) character instead of double or single quotes. Template literals can contain place holders.
These are indicated by the Dollar sign and curly braces (`${expression}`).

The expressions in the place holders and the text between them get passed to a function.
The default function just concatenates the parts into a single string.

If there is an expression preceding the template literal (`tag` here),  the template string is called "tagged template literal".
 
In that case, the tag expression (usually a function) gets called with the processed template literal, which you can then manipulate before outputting.
To escape a back-tick in a template literal, put a backslash __\__ before the back-tick.

>```
> `\`` === '`' // --> true
>```


#### Multi-line Strings

Any new line characters inserted in the source are part of the template literal.
Using normal strings, you would have to use the following syntax in order to get multi-line strings:

>```
> console.log('string text line 1\n' +
> 'string text line 2');
> // "string text line 1
> // string text line 2"
>```

To get the same effect with multi-line strings, you can now write:

>```
> console.log(`string text line 1
> string text line 2`);
> // "string text line 1
> // string text line 2"
>```


#### Expression Interpolation

In order to embed expressions within normal strings, you would use the following syntax:

>```
> var a = 5;
> var b = 10;
> console.log('Fifteen is ' + (a + b) + ' and\nnot ' + (2 * a + b) + '.');
> // "Fifteen is 15 and
> // not 20."
>```

Now, with template literals, you are able to make use of the syntactic sugar making substitutions like this more readable:

>```
> var a = 5;
> var b = 10;
> console.log(`Fifteen is ${a + b} and
> not ${2 * a + b}.`);
> // "Fifteen is 15 and
> // not 20."
>```


#### Nesting Templates

In certain times, nesting a template is the easiest and perhaps more readable way to have configurable strings. 
Within a backticked template it is simple to allow inner backticks simply by adding parenthesis ${( )} within the template.

For instance, if condition a is true: then return this templated literal.

In ES5:

>```
> var classes = 'header'
> classes += (isLargeScreen() ?
>    '' : item.isCollapsed ?
>      ' icon-expander' : ' icon-collapser');
>```

In ES2015 with template literals and without nesting:

>```
> const classes = `header ${ isLargeScreen() && item.isCollapsed ?
>     'icon-expander' : 'icon-collapser' }`;
>```

In ES2015 with nested template literals:

>```
> const classes = `header ${( isLargeScreen() &&
>  `icon-${item.isCollapsed ? 'expander' : 'collapser'}` )}`;
>```


#### Tagged Template Literals

A more advanced form of template literals are _tagged_ template literals.
Tags allow you to parse template literals with a function.
The first argument of a tag function contains an array of string values.

In the end, your function can return your manipulated string (or it can return something completely different as described in the next example). 

The name of the function used for the tag can be named whatever you want.

>```
> var person = 'Mike';
> var age = 28;
> 
> function myTag(strings, personExp, ageExp) {
> 
>   var str0 = strings[0]; // "that "
>   var str1 = strings[1]; // " is a "
> 
>   // There is technically a string after
>   // the final expression (in our example),
>   // but it is empty (""), so disregard.
>   // var str2 = strings[2];
> 
>   var ageStr;
>   if (ageExp > 99){
>     ageStr = 'centenarian';
>   } else {
>     ageStr = 'youngster';
>   }
> 
>   return str0 + personExp + str1 + ageStr;
> 
> }
> 
> var output = myTag`that ${ person } is a ${ age }`;
> 
> console.log(output);
> // that Mike is a youngster
>```

Tag functions don't need to return a string, as shown in the following example.

>```
> function template(strings, ...keys) {
>   return (function(...values) {
>     var dict = values[values.length - 1] || {};
>     var result = [strings[0]];
>     keys.forEach(function(key, i) {
>       var value = Number.isInteger(key) ? values[key] : dict[key];
>       result.push(value, strings[i + 1]);
>     });
>     return result.join('');
>   });
> }
>
> var t1Closure = template`${0}${1}${0}!`;
> t1Closure('Y', 'A');  // "YAY!"
> var t2Closure = template`${0} ${'foo'}!`;
> t2Closure('Hello', {foo: 'World'});  // "Hello World!"
>```


#### Raw Strings

The special `raw` property, available on the first function argument of tagged template literals, allows you to access the raw strings as they were entered, without processing escape sequences.

>```
> function tag(strings, ...values) {
>   console.log(strings.raw[0]);
> }
> 
> tag`string text line 1 \n string text line 2`;
> // logs "string text line 1 \n string text line 2" ,
> // including the two characters '\' and 'n'
>```

In addition, the `String.raw()` method exists to create raw strings just like the default template function and string concatenation would create.

>```
> var str = String.raw`Hi\n${2+3}!`;
> // "Hi\n5!"
>
> str.length;
> // 6
>
> str.split('').join(',');
> // "H,i,\,n,5,!"
>```


#### Tagged Template Literals and Escape Sequences

 As of ES2016, tagged template literals conform to the rules of the following escape sequences:
 
 - Unicode escapes started by "\u", for example \u00A9
 - Unicode code point escapes indicated by "\u{}", for example \u{2F804}
 - Hexadecimal escapes started by "\x", for example \xA9
 - Octal literal escapes started by "\" and (a) digit(s), for example \251

This means that a tagged template like the following is problematic, because, per ECMAScript grammar, a parser looks for valid Unicode escape sequences, but finds malformed syntax:
 
>```
> latex`\unicode`
> // Throws in older ECMAScript versions (ES2016 and earlier)
> // SyntaxError: malformed Unicode character escape sequence
>```

Tagged template literals should allow the embedding of languages (for example DSLs, or LaTeX), where other escapes sequences are common. The ECMAScript proposal Template Literal Revision (stage 4, to be integrated in the ECMAScript 2018 standard) removes the syntax restriction of ECMAScript escape sequences from tagged template literals.

However, illegal escape sequence must still be represented in the "cooked" representation. 

They will show up as `undefined` element in the "cooked" array:

>```
> function latex(str) { 
>  return { "cooked": str[0], "raw": str.raw[0] }
> } 
> 
> latex`\unicode`
> 
> // { cooked: undefined, raw: "\\unicode" }
>```

Note that the escape sequence restriction is only dropped from `tagged` template literals and not from `untagged` template literals:

>```
> let bad = `bad escape sequence: \unicode`;
>```


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


**Spread in array literals**

A more powerful array literal

 Without spread syntax, to create a new array using an existing array as one part of it, the array literal syntax is no longer sufficient and imperative code must be used instead using a combination of push, splice, concat, etc.
 With spread syntax this becomes much more succinct:

>```
> var parts = ['shoulders', 'knees']; 
> var lyrics = ['head', ...parts, 'and', 'toes'];
> // ["head", "shoulders", "knees", "and", "toes"]
>```

Just like spread for argument lists, ... can be used anywhere in the array literal and it can be used multiple times.


**Copy an array**

>```
> var arr = [1, 2, 3];
> var arr2 = [...arr]; // like arr.slice()
> arr2.push(4); 
> 
> // arr2 becomes [1, 2, 3, 4]
> // arr remains unaffected
>```

*Note:* Spread syntax effectively goes one level deep while copying an array.
Therefore, it may be unsuitable for copying multidimensional arrays as the following example shows (it's the same with Object.assign() and spread syntax).

>```
> var a = [[1], [2], [3]];
> var b = [...a];
> b.shift().shift(); // 1
> // Now array a is affected as well: [[], [2], [3]]
>```


**A better way to concatenate arrays**

 Array.concat is often used to concatenate an array to the end of an existing array. Without spread syntax this is done as:

>```
> var arr1 = [0, 1, 2];
> var arr2 = [3, 4, 5];
> // Append all items from arr2 onto arr1
> arr1 = arr1.concat(arr2);
>```

 With spread syntax this becomes:

>```
> var arr1 = [0, 1, 2];
> var arr2 = [3, 4, 5];
> arr1 = [...arr1, ...arr2];
>```

 Array.unshift is often used to insert an array of values at the start of an existing array. Without spread syntax this is done as:
 
>```
> var arr1 = [0, 1, 2];
> var arr2 = [3, 4, 5];
> // Prepend all items from arr2 onto arr1
> Array.prototype.unshift.apply(arr1, arr2) // arr1 is now [3, 4, 5, 0, 1, 2]
>```

 With spread syntax this becomes:

>```
> var arr1 = [0, 1, 2];
> var arr2 = [3, 4, 5];
> arr1 = [...arr2, ...arr1]; // arr1 is now [3, 4, 5, 0, 1, 2]
>```


**Spread in object literals**

 The Rest/Spread Properties for ECMAScript proposal (stage 3) adds spread properties to object literals.
 It copies own enumerable properties from a provided object onto a new object.

 Shallow-cloning (excluding prototype) or merging of objects is now possible using a shorter syntax than Object.assign().
 
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

*Note* that Object.assign() triggers setters whereas spread syntax doesn't.


Only for iterables

 Spread syntax (other than in the case of spread properties) can be applied only to iterable objects:
 
>```
> var obj = {'key1': 'value1'};
> var array = [...obj]; // TypeError: obj is not iterable
>```


Spread with many values

 When using spread syntax for function calls, be aware of the possibility of exceeding the JavaScript engine's argument length limit.
 See apply() for more details.
 

Rest syntax (parameters)

 Rest syntax looks exactly like spread syntax, but is used for destructuring arrays and objects.
 
 In a way, rest syntax is the opposite of spread syntax:
 spread 'expands' an array into its elements, while rest collects multiple elements and 'condenses' them into a single element.
 
 
### Function Expression

 The function keyword can be used to define a function inside an expression.

 You can also define functions using the Function constructor and a function declaration.

 Syntax
 
 var myFunction = function [name]([param1[, param2[, ..., paramN]]]) {
   statements
};

 As of ES2015, you can also use arrow functions.
 
 Parameters
 
 name
 The function name. Can be omitted, in which case the function is anonymous. The name is only local to the function body.


 paramN
 The name of an argument to be passed to the function.


 statements
 The statements which comprise the body of the function.

 A function expression is very similar to and has almost the same syntax as a function statement
 (see function statement for details). The main difference between a function expression and a function statement is the function name,  which can be omitted in function expressions to create anonymous functions.
 A function expression can be used as a IIFE (Immediately Invoked Function Expression) which runs as soon as it is defined.
 
 
#### Function Expression Hoisting
 
  Function expressions in JavaScript are not hoisted, unlike function declarations.
  You can't use function expressions before you define them:
  
>```
> notHoisted(); // TypeError: notHoisted is not a function
>
> var notHoisted = function() {
>    console.log('bar');
> };
>```

#### Named Function Expression

 If you want to refer to the current function inside the function body, you need to create a named function expression.
 This name is then local only to the function body (scope).
 This also avoids using the non-standard arguments.callee property.

>```
> var math = {
>   'factorial': function factorial(n) {
>     if (n <= 1)
>       return 1;
>     return n * factorial(n - 1);
>   }
> };
>```

 The variable assigned to a function expression will have a `name` property.
 The name doesn't change if it's assigned to a different variable.
 If function name is ommited, it will be the variable name (implicit name).
 If function name presets, it will be the function name (explicit name).
 This also applies to `arrow functions` (arrows don't have a name so you can only give the variable an implicit name).

>```
> var foo = function() {}
> foo.name // "foo"
>
> var foo2 = foo
> foo2.name // "foo"
>
> var bar = function baz() {}
> bar.name // "baz"
>```

**_Examples_**

The following example defines an unnamed function and assigns it to x. The function returns the square of its argument:

>```
> var x = function(y) {
>    return y * y;
> };
>```

More commonly it is used as a callback:

>```
> button.addEventListener('click', function(event) {
> console.log('button is clicked!')
> })
>```


### Function* Expression

The `function*` keyword can be used to define a generator function inside an expression.

**_Syntax_**
>```
> function* [name]([param1[, param2[, ..., paramN]]]) {
>    statements
> }
>```


**_Parameters_**

**name**
The function name. Can be omitted, in which case the function is anonymous. 
The name is only local to the function body.

**paramN**
The name of an argument to be passed to the function. A function can have up to 255 arguments.

**statements**
The statements which comprise the body of the function.


A `function*` expression is very similar to and has almost the same syntax as a `function*` statement. The main difference between a `function*` expression and a `function*` statement is the _function name_, which can be omitted in `function*` expressions to create `anonymous` functions.


**_Examples_**
The following example defines an unnamed generator function and assigns it to x. The function yields the square of its argument:

>```
> var x = function*(y) {
>    yield y * y;
> };
>```


### Async Function Expression

 The **`async function`** keyword can be used to define `async` functions inside expressions.
 You can also define async functions using an async function statement.
 
**_Syntax_**
>```
> async function [name]([param1[, param2[, ..., paramN]]]) {
>    statements
> }
>```


As of ES2015, you can also use arrow functions.

**_Parameters_**

**name**
 The function name. Can be omitted, in which case the function is anonymous. The name is only local to the function body.

**paramN**
 The name of an argument to be passed to the function.
 
**statements**
 The statements which comprise the body of the function.


An `async function` expression is very similar to, and has almost the same syntax as, an `async function` statement.
The main difference between an `async function` expression and an `async function` statement is the function name, which can be omitted in `async function`
An async function expression can be used as an IIFE (Immediately Invoked Function Expression) 
expressions to create *anonymous* functions. 

An `async function` expression can be used as an IIFE (Immediately Invoked Function Expression) which runs as soon as it is defined.


**_Examples_**

**Simple example**
>```
> function resolveAfter2Seconds(x) {
>   return new Promise(resolve => {
>     setTimeout(() => {
>       resolve(x);
>     }, 2000);
>   });
> };
>
> (async function(x) { // async function expression used as an IIFE
>   var a = resolveAfter2Seconds(20);
>   var b = resolveAfter2Seconds(30);
>   return x + await a + await b;
> })(10).then(v => {
>   console.log(v);  // prints 60 after 2 seconds.
> });
>
> var add = async function(x) { // async function expression assigned to a variable
>   var a = await resolveAfter2Seconds(20);
>   var b = await resolveAfter2Seconds(30);
>   return x + a + b;
> };
>
> add(10).then(v => {
>   console.log(v);  // prints 60 after 4 seconds.
> });
>```

### Class Expression

The **class expression** is one way to define a class in ECMAScript 2015.
Similar to function expressions, class expressions can be named or unnamed.
If named, the name of the class is local to the class body only. 
JavaScript classes are using prototype-based inheritance.

**_Syntax_**
>```
> var MyClass = class [className] [extends] {
>   // class body
> };
>```

A class expression has a similar syntax to a class statement (declaration).
However, with class expressions, you are able to omit the class name ("binding identifier"), which you can't with class statements. 

Additionally, class expressions allow you to redefine/re-declare classes and don't throw any type errors like class declaration. 

The constructor property is optional.
And, `typeof` the classes generated using this keyword will always be "function".


Just like with class statements, the class body of class expressions is executed in strict mode.

>```
> 'use strict';
> var Foo = class {}; // constructor property is optional
> var Foo = class {}; // Re-declaration is allowed
>
> typeof Foo; //returns "function"
> typeof class {}; //returns "function"
> 
> Foo instanceof Object; // true
> Foo instanceof Function; // true
> class Foo {}; // Throws TypeError, doesn't allow re-declaration
>```


**_Examples_**

**A simple class expression**
This is just a simple anonymous class expression which you can refer to using the variable "Foo".

>```
> var Foo = class {
>   constructor() {}
>   bar() {
>     return 'Hello World!';
>   }
> };
> 
> var instance = new Foo();
> instance.bar(); // "Hello World!"
> Foo.name; // "Foo"
>```


**Named class expressions**

If you want to refer to the current class inside the class body, you can create a named class expression. This name is only visible in the scope of the class expression itself.

>```
> var Foo = class NamedFoo {
>   constructor() {}
>   whoIsThere() {
>     return NamedFoo.name;
>   }
> }
> var bar = new Foo();
> bar.whoIsThere(); // "NamedFoo"
> NamedFoo.name; // ReferenceError: NamedFoo is not defined
> Foo.name; // "NamedFoo"
>```

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


### String

 The `String` global object is a constructor for strings, or a sequence of characters.
 
**_Syntax_**
 String literals take the forms:

>```
> 'string text'
> "string text"
> "中文 español deutsch English हिन्दी العربية português বাংলা русский 日本語 ਪੰਜਾਬੀ 한국어 தமிழ் עברית"
>```

Strings can also be created using the String global object directly:

>```
> String(thing)
>```


**_Parameters_**

**`thing`**
 Anything to be converted to a string. 


Strings are useful for holding data that can be represented in text form.  
Some of the most-used operations on strings are to check their `length`,  
to build and concatenate them using the + and += string operators,  
checking for the existence or location of substrings with the indexOf() method,   
or extracting substrings with the substring() method.


**_Properties_**

** `String.prototype` **
    Allows the addition of properties to a String object. 


**_Methods_**

** `String.fromCharCode()` **
    Returns a string created by using the specified sequence of Unicode values.
    
** `String.fromCodePoint()` **
    Returns a string created by using the specified sequence of code points.    
    
** `String.raw()` **
    Returns a string created from a raw template string.   


#### Character Access

 There are two ways to access an individual character in a string.
 
  The first is the charAt() method:

>```
> return 'cat'.charAt(1); // returns "a"
>```

 The other way (introduced in ECMAScript 5) is to treat the string as an array-like object, where individual characters correspond to a numerical index:

>```
> return 'cat'[1]; // returns "a"
>```

 For character access using bracket notation, attempting to delete or assign a value to these properties will not succeed.
 The properties involved are neither writable nor configurable.
 

#### Comparing Strings

 C developers have the strcmp() function for comparing strings.
 In JavaScript, you just use the less-than and greater-than operators:
 
>```
> var a = 'a';
> var b = 'b';
> 
> if (a < b) { // true
>   console.log(a + ' is less than ' + b);
> } else if (a > b) {
>   console.log(a + ' is greater than ' + b);
> } else {
>   console.log(a + ' and ' + b + ' are equal.');
> }
>```

A similar result can be achieved using the `localeCompare()` method inherited by `String` instances.
 
 
#### Distinction between String Primitives and `String` Objects

 Note that JavaScript distinguishes between `String` objects and primitive string values. 
 (The same is true of `Boolean` and `Numbers`.)

 String literals (denoted by double or single quotes) and strings returned from `String` calls in a non-constructor context (i.e., without using the `new` keyword) are primitive strings.
 JavaScript automatically converts primitives to `String` objects, so that it's possible to use `String` object methods for primitive strings.
 
 In contexts where a method is to be invoked on a primitive string or a property lookup occurs, JavaScript will automatically wrap the string primitive and call the method or perform the property lookup.
 
 
>```
> var s_prim = 'foo';
> console.log(typeof s_prim); // Logs "string"
>
> var s_obj = new String(s_prim);
> console.log(typeof s_obj);  // Logs "object"
>```


 String primitives and `String` objects also give different results when using `eval()`.
 Primitives passed to `eval` are treated as source code;
 `String` objects are treated as all other objects are, by returning the object
 
**For example:**
>``` 
> var s1 = '2 + 2';             // creates a string primitive
> console.log(eval(s1));        // returns the number 4
>
> var s2 = new String('2 + 2'); // creates a String object
> console.log(eval(s2));        // returns the string "2 + 2"
>```

For these reasons, code may break when it encounters `String` objects when it expects a primitive string instead, although generally authors need not worry about the distinction.

A `String` object can always be converted to its primitive counterpart with the `valueOf()` method.

>```
> console.log(eval(s2.valueOf())); // returns the number 4
>```

#### Long Literal Strings

 Sometimes, your code will include strings which are very long.
 Rather than having lines that go on endlessly, or wrap at the whim of your editor, you may wish to specifically break the string into multiple lines in the source code without affecting the actual string contents.
 
 There are two ways you can do this.
 
 You can use the + operator to append multiple strings together, like this:

>```
> let longString = "This is a very long string which needs " +
>                 "to wrap across multiple lines because " +
>                 "otherwise my code is unreadable.";
>```

 Or you can use the backslash character ("\") at the end of each line to indicate that the string will continue on the next line.
 
 Make sure there is no space or any other character after the backslash (except for a line break), or as an indent; 
 otherwise it will not work. That form looks like this:
 
>```
> let longString = "This is a very long string which needs \
>                   to wrap across multiple lines because \
>                   otherwise my code is unreadable.";
>```

 Both of these result in identical strings being created.


#### Escape Notation
 
 Beside regular, printable characters, special characters can be encoded using escape notation:

|   Code        |	  Output                  |
|  :---:        | --------------------------- |
|   \0 	        |   the NULL character        |
|   \' 	        |   single quote              |
|   \" 	        |   double quote              |
|   \\ 	        |   backslash                 |
|   \n 	        |   new line                  |
|   \r 	        |   carriage return           |
|   \v 	        |   vertical tab              |
|   \t 	        |   tab                       |
|   \b 	        |   backspace                 |
|   \f 	        |   form feed                 |
|   \uXXXX 	    |   unicode codepoint         |
|   \u{X} ...   |   unicode codepoint         |
|   \u{XXXXXX}  | 	                          |
|   \xXX 	    |   the Latin-1 character     |
 
 Unlike some other languages, JavaScript makes no distinction between single-quoted strings and double-quoted strings; therefore, the escape sequences above work in strings created with either single or double quotes.
 

#### Template Literals

Starting with ECMAScript 2015, string literals can also be so-called Template literals:

>```
> `hello world`
> `hello!
>  world!`
> `hello ${who}`
> escape `<a>${who}</a>`
>```


### Number

The **`Number`** JavaScript object is a wrapper object allowing you to work with numerical values.  
A `Number` object is created using the `Number()` constructor.


**Syntax**

>```
> new Number(value);
>```

* **Parameters**

**`value`**
 
 The numeric value of the object being created. 
    

**Description**

The primary uses for the `Number` object are:

* If the argument cannot be converted into a number, it returns `NaN`.  

* In a non-constructor context (i.e., without the `new` operator), `Number` can be used to perform a type conversion.


**Properties**

**`Number.EPSILON`**

 The smallest interval between two representable numbers.
    
**`Number.MAX_SAFE_INTEGER`**

 The maximum safe integer in JavaScript (`2^53 - 1`).
    
**`Number.MAX_VALUE`**
    
 The largest positive representable number.
    
**`Number.MIN_SAFE_INTEGER`**

 The minimum safe integer in JavaScript (`-(2^53 - 1)`).
    
**`Number.MIN_VALUE`**

 The smallest positive representable number - that is, the positive number closest to zero (without actually being zero).
    
**`Number.NaN`**

 Special "not a number" value.
    
**`Number.NEGATIVE_INFINITY`**

 Special value representing negative infinity;  returned on overflow.
    
**`Number.POSITIVE_INFINITY`**

 Special value representing infinity;  
 returned on overflow.
    
**`Number.prototype`**

 Allows the addition of properties to a **`Number`** object. 
    

**Methods**

**`Number.isNaN()`**

 Determine whether the passed value is `NaN`.
    
**`Number.isFinite()`**

 Determine whether the passed value is a finite number.
    
**`Number.isInteger()`**

 Determine whether the passed value is an integer.
    
**`Number.isSafeInteger()`**

 Determine whether the passed value is a safe integer (number between `-(2^53 - 1)` and `2^53 - 1`).

**`Number.parseFloat()`**

 The value is the same as `parseFloat()` of the global object.
    
**`Number.parseInt()`**

 The value is the same as `parseInt()` of the global object. 


**`Number` instances**

All `Number` instances inherit from `Number.prototype`.  
The prototype object of the `Number` constructor can be modified to affect all `Number` instances.

**Methods**

**`Number.prototype.toExponential()`**

 Returns a string representing the number in exponential notation.
    
**`Number.prototype.toFixed()`**

 Returns a string representing the number in fixed-point notation.
    
**`Number.prototype.toLocaleString()`**

 Returns a string with a language sensitive representation of this number.  
 Overrides the `Object.prototype.toLocaleString()` method.
    
**`Number.prototype.toPrecision()`**

 Returns a string representing the number to a specified precision in fixed-point or exponential notation.
    
**`Number.prototype.toSource()`**

 Returns an object literal representing the specified Number object; you can use this value to create a new object.  
 Overrides the `Object.prototype.toSource()` method.
    
**`Number.prototype.toString()`**

 Returns a string representing the specified object in the specified radix (base).  
 Overrides the `Object.prototype.toString()` method.
    
**`Number.prototype.valueOf()`**
   
 Returns the primitive value of the specified object.  Overrides the `Object.prototype.valueOf()` method.


**Examples**

* **Using the `Number` object to assign values to numeric variables**

The following example uses the `Number` object's properties to assign values to several numeric variables:

>```
> var biggestNum = Number.MAX_VALUE;
> var smallestNum = Number.MIN_VALUE;
> var infiniteNum = Number.POSITIVE_INFINITY;
> var negInfiniteNum = Number.NEGATIVE_INFINITY;
> var notANum = Number.NaN;
>```

* **Integer range for `Number`**

The following example shows the minimum and maximum integer values that can be represented as `Number` object  (for details, refer to ECMAScript standard, chapter 6.1.6 The Number Type):

>```
> var biggestInt = 9007199254740991;
> var smallestInt = -9007199254740991;
>```

When parsing data that has been serialized to JSON, integer values falling out of this range can be expected to become corrupted when JSON parser coerces them to Number type.  
Using `String` instead is a possible workaround.

* **Using `Number` to convert a `Date` object**

The following example converts the `Date` object to a numerical value using `Number` as a function:

>```
> var d = new Date('December 17, 1995 03:24:00');
> console.log(Number(d));
>```

This logs "819199440000".

* **Convert numeric strings to numbers**

>```
> Number('123')     // 123
> Number('12.3')    // 12.3
> Number('')        // 0
> Number('0x11')    // 17
> Number('0b11')    // 3
> Number('0o11')    // 9
> Number('foo')     // NaN
> Number('100a')    // NaN
>```


### Function

 The __`Function` constructor__ creates a new `Function` object. 
 Calling the constructor directly can create functions dynamically, but suffers from security and performance issues similar to `eval`.

 Every JavaScript function is actually a `Function` object.

**_Syntax_**

>```
> new Function ([arg1[, arg2[, ...argN]],] functionBody)
>```

 **Parameters**

**`arg1, arg2, ... argN`**

Names to be used by the function as formal argument names.
    
Each must be a string that corresponds to a valid JavaScript identifier or a list of such strings separated with a comma; for example "`x`", "`theValue`", or "`a,b`".
    
    
**`functionBody`**

A string containing the JavaScript statements comprising the function definition.


 `Function` objects created with the `Function` constructor are parsed when the function is created.
 This is less efficient than declaring a function with a function expression or function statement and calling it within your code, because such functions are parsed with the rest of the code.
 
 All arguments passed to the function are treated as the names of the identifiers of the parameters in the function to be created, in the order in which they are passed.
 
 Invoking the `Function` constructor as a function (without using the new operator) has the same effect as invoking it as a constructor.
 
 
 **_Properties and Methods of `Function`_**
 The global `Function` object has no methods or properties of its own.
 
 However, since it is a function itself, it does inherit some methods and properties through the prototype chain from `Function.prototype`.
 
 
 **_`Function` prototype object_**
 
 **Properties**

**`Function.arguments`**
        
    An array corresponding to the arguments passed to a function. This is deprecated as property of `Function`. Use the `arguments` object available within the function instead.
 
**`Function.length`**

    Specifies the number of arguments expected by the function.
 
**`Function.name`**

    The name of the function.
        
**`Function.prototype.constructor`**

    Specifies the function that creates an object's prototype.

 **Methods**

**`Function.prototype.apply()`**

    Calls a function and sets its this to the provided value, arguments can be passed as an  `Array` object.

**`Function.prototype.bind()`**

    Creates a new function which, when called, has its this set to the provided value, with a given sequence of arguments preceding any provided when the new function was called.
    
**`Function.prototype.call()`**

    Calls (executes) a function and sets its this to the provided value, arguments can be passed as they are.
        
**`Function.prototype.toString()`**

    Returns a string representing the source code of the function. Overrides the `Object.prototype.toString` method.
        
     
**_`Function` instances_**

`Function` instances inherit methods and properties from `Function.prototype`.

As with all constructors, you can change the constructor's prototype object to make changes to all `Function` instances.
    

**Examples**
        
Specifying arguments with the `Function` constructor
The following code creates a `Function` object that takes two arguments.

>```
> // Example can be run directly in your JavaScript console
> 
> // Create a function that takes two arguments and returns the sum of those arguments
> var adder = new Function('a', 'b', 'return a + b');
> 
> // Call the function
> adder(2, 6);
> // > 8
>```

 The arguments "`a`" and "`b`" are formal argument names that are used in the function body, "`return a + b`".
        
    
Difference between Function constructor and function declaration

Functions created with the `Function` constructor do not create closures to their creation contexts; they always are created in the global scope. 

When running them, they will only be able to access their own local variables and global ones, not the ones from the scope in which the `Function` constructor was called. 

This is different from using `eval` with code for a function expression.
    
>```
> var x = 10;
> 
> function createFunction1() {
>     var x = 20;
>     return new Function('return x;'); // this |x| refers global |x|
> }
> 
> function createFunction2() {
>     var x = 20;
>     function f() {
>         return x; // this |x| refers local |x| above
>     }
>     return f;
> }
> 
> var f1 = createFunction1();
> console.log(f1());          // 10
> var f2 = createFunction2();
> console.log(f2());          // 20
>```

### Object

 The `Object` constructor creates an object wrapper.
 
 **_Syntax_**

>```
> // Object initialiser or literal
> { [ nameValuePair1[, nameValuePair2[, ...nameValuePairN] ] ] }
> 
> // Called as a constructor
> new Object([value])
>```

 **Parameters**

 **`nameValuePair1, nameValuePair2, ... nameValuePairN`**
 
    Pairs of names (strings) and values (any value) where the name is separated from the value by a colon.

 **`value`**
 
    Any value.


 The `Object` constructor creates an object wrapper for the given value.
 If the value is null or undefined, it will create and return an empty object, otherwise, it will return an object of a Type that corresponds to the given value.
 If the value is an object already, it will return the value.
 
 When called in a non-constructor context, `Object` behaves identically to `new Object()`.


 **_Properties of the `Object` constructor_**
 
**`Object.length`**

    Has a value of 1.
        
**`Object.prototype`**

    Allows the addition of properties to all objects of type Object.


 **_Methods of the `Object` constructor_**
 
**`Object.assign()`**

    Copies the values of all enumerable own properties from one or more source objects to a target object.
    
**`Object.create()`**

    Creates a new object with the specified prototype object and properties.

**`Object.defineProperty()`**

    Adds the named property described by a given descriptor to an object.
    
**`Object.defineProperties()`**

    Adds the named properties described by the given descriptors to an object.
    
**`Object.entries()`**

    Returns an array of a given object's own enumerable property `[key, value]` pairs.
    
**`Object.freeze()`**

    Freezes an object: other code can't delete or change any properties.
        
**`Object.getOwnPropertyDescriptor()`**

    Returns a property descriptor for a named property on an object.
        
**`Object.getOwnPropertyDescriptors()`**

    Returns an object containing all own property descriptors for an object.
        
**`Object.getOwnPropertyNames()`**

    Returns an array containing the names of all of the given object's __own__ enumerable and non-enumerable properties.
    
**`Object.getOwnPropertySymbols()`**

    Returns an array of all symbol properties found directly upon a given object.
        
**`Object.getPrototypeOf()`**

    Returns the prototype of the specified object.
    
**`Object.is()`**

    Compares if two values are the same value. 
    Equates all NaN values (which differs from both Abstract Equality Comparison and Strict Equality Comparison).
    
**`Object.isExtensible()`**

    Determines if extending of an object is allowed.
        
**`Object.isFrozen()`**

    Determines if an object was frozen
    
**`Object.isSealed()`**

    Determines if an object is sealed.
        
**`Object.keys()`**

    Returns an array containing the names of all of the given object's __own__ enumerable properties.
        
**`Object.preventExtensions()`**
    
    Prevents any extensions of an object. 
        
**`Object.seal()`**

    Prevents other code from deleting properties of an object.
    
**`Object.setPrototypeOf()`**

    Sets the prototype (i.e., the internal `[[Prototype]]` property)
    
**`Object.values()`**

    Returns an array of a given object's own enumerable values.


**_`Object` instances and `Object` prototype object_**

 All objects in JavaScript are descended from `Object`;
 all objects inherit methods and properties from `Object.prototype`, 
 although they may be overridden.
 
 For example, other constructors' prototypes override the `constructor` property and provide their own `toString()` methods.
 Changes to the `Object` prototype object are propagated to all objects unless the properties and methods subject to those changes are overridden further along the prototype chain.


**Properties**

**`Object.prototype.constructor`**

    Specifies the function that creates an object's prototype.


**Methods**
    
**`Object.prototype.hasOwnProperty()`**

    Returns a boolean indicating whether an object contains the specified property as a direct property of that object and not inherited through the prototype chain.

**`Object.prototype.isPrototypeOf()`**

    Returns a boolean indicating whether the object this method is called upon is in the prototype chain of the specified object.
        
**`Object.prototype.propertyIsEnumerable()`**

    Returns a boolean indicating if the internal ECMAScript [[Enumerable]] attribute is set.
        
**`Object.prototype.toLocaleString()`**

    Calls toString().

**`Object.prototype.toString()`**

    Returns a string representation of the object.
        
**`Object.prototype.valueOf()`**

    Returns the primitive value of the specified object.

**_Examples_**
    
Using `Object` given `undefined` and `null` types  
The following examples store an empty `Object` object in `o`:
        
>```
> var o = new Object();
>```


>```
> var o = new Object(undefined);
>```


>```
> var o = new Object(null);
>```
    
Using `Object` to create `Boolean` objects
The following examples store `Boolean` objects in `o`:

>```
> // equivalent to o = new Boolean(true);
> var o = new Object(true);
>```


>```
> // equivalent to o = new Boolean(false);
> var o = new Object(Boolean());
>```
   
   
### Array
 The JavaScript `Array` object is a global object that is used in the construction of arrays; which are high-level, list-like objects.

**_Syntax_**

>```
> [element0, element1, ..., elementN]
> new Array(element0, element1[, ...[, elementN]])
> new Array(arrayLength)
>```

**Parameters**

**`elementN`**

A JavaScript array is initialized with the given elements, 
except in the case where a single argument is passed to the `Array` constructor and that argument is a number (see the arrayLength parameter below).

Note that this special case only applies to JavaScript arrays created with the `Array` constructor, not array literals created with the bracket syntax.

**`arrayLength`**

If the only argument passed to the `Array` constructor is an integer between 0 and 232-1 (inclusive), this returns a new JavaScript array with its `length` property set to that number

(Note: this implies an array of `arrayLength` empty slots, not slots with actual `undefined` values).

If the argument is any other number, a `RangeError` exception is thrown.

**_Using_**

    Create an Array
    
>```
> var fruits = ['Apple', 'Banana'];
> 
> console.log(fruits.length);
> // 2
>```

    Access (index into) an Array item
    
>```
> var first = fruits[0];
> // Apple
> 
> var last = fruits[fruits.length - 1];
> // Banana
>```

    Loop over an Array

>```
> fruits.forEach(function(item, index, array) {
>   console.log(item, index);
> });
> // Apple 0
> // Banana 1
>```

    Add to the end of an Array

>```
> var newLength = fruits.push('Orange');
> // ["Apple", "Banana", "Orange"]
>```

    Remove from the end of an Array

>```
> var last = fruits.pop(); // remove Orange (from the end)
> // ["Apple", "Banana"];
>```

    Remove from the front of an Array

>```
> var first = fruits.shift(); // remove Apple from the front
> // ["Banana"];
>```

    Add to the front of an Array

>```
> var newLength = fruits.unshift('Strawberry') // add to the front
> // ["Strawberry", "Banana"];
>```

    Find the index of an item in the Array

>```
> fruits.push('Mango');
> // ["Strawberry", "Banana", "Mango"]
> 
> var pos = fruits.indexOf('Banana');
> // 1
>```

    Remove an item by index position

>```
> var removedItem = fruits.splice(pos, 1); // this is how to remove an item
>                                         
> // ["Strawberry", "Mango"]
>```

    Remove items from an index position

>```
> var vegetables = ['Cabbage', 'Turnip', 'Radish', 'Carrot'];
> console.log(vegetables); 
> // ["Cabbage", "Turnip", "Radish", "Carrot"]
> 
> var pos = 1, n = 2;
> 
> var removedItems = vegetables.splice(pos, n); 
> // this is how to remove items, n defines the number of items to be removed,
> // from that position(pos) onward to the end of array.
> 
> console.log(vegetables); 
> // ["Cabbage", "Carrot"] (the original array is changed)
> 
> console.log(removedItems); 
> // ["Turnip", "Radish"]
>```

    Copy an Array

>```
> var shallowCopy = fruits.slice(); // this is how to make a copy
> // ["Strawberry"]
>```


 Arrays are list-like objects whose prototype has methods to perform traversal and mutation operations. 
 Neither the length of a JavaScript array nor the types of its elements are fixed.
 Since an array's length can change at any time, and data can be stored at non-contiguous locations in the array, JavaScript arrays are not guaranteed to be dense; this depends on how the programmer chooses to use them.
 
 In general, these are convenient characteristics; but if these features are not desirable for your particular use, you might consider using typed arrays.
 
 
 Arrays cannot use strings as element indexes, but must use integers.
 Setting or accessing via non-integers using bracket notation (or dot notation) will not set or retrieve an element from the array list itself, but will set or access a variable associated with that array's object property collection.
 The array's object properties and list of array elements are separate, and the array's traversal and mutation operations cannot be applied to these named properties.
 

 ** Accessing array elements **
 
    JavaScript arrays are zero-indexed: the first element of an array is at index `0`, and the last element is at the index equal to the value of the array's `length` property minus 1.

>```
> var arr = ['this is the first element', 'this is the second element'];
> console.log(arr[0]);              // logs 'this is the first element'
> console.log(arr[1]);              // logs 'this is the second element'
> console.log(arr[arr.length - 1]); // logs 'this is the last element'
>```

    Array elements are object properties in the same way that `toString` is a property, but trying to access an element of an array as follows throws a syntax error
    because the property name is not valid:
    
>```
> console.log(arr.0); // a syntax error
>```
    
    There is nothing special about JavaScript arrays and the properties that cause this.
    JavaScript properties that begin with a digit cannot be referenced with dot notation; and must be accessed using bracket notation.
    
For example, if you had an object with a property named '3d', it can only be referenced using bracket notation.

E.g.:
>```
> var years = [1950, 1960, 1970, 1980, 1990, 2000, 2010];
> console.log(years.0);   // a syntax error
> console.log(years[0]);  // works properly
>```

>```
> renderer.3d.setTexture(model, 'character.png');     // a syntax error
> renderer['3d'].setTexture(model, 'character.png');  // works properly
>```

Note that in the `3d` example, `'3d'` had to be quoted.
It's possible to quote the JavaScript array indexes as well (e.g., years['2'] instead of years[2]), although it's not necessary. 

The 2 in `years[2]` is coerced into a string by the JavaScript engine through an implicit `toString` conversion.
It is for this reason that `'2'` and `'02'` would refer to two different slots on the `years` object and the following example could be `true`:

>```
> console.log(years['2'] != years['02']);
>```

Similarly, object properties which happen to be reserved words(!) can only be accessed as string literals in bracket notation(but it can be accessed by dot notation in firefox 40.0a2 at least):

>```
> var promise = {
>   'var'  : 'text',
>   'array': [1, 2, 3, 4]
> };
>
> console.log(promise['var']);
>```


 ** Relationship between `length` and numerical properties ** 

    A JavaScript array's `length` property and numerical properties are connected.
    Several of the built-in array methods (e.g., `join`, `slice`, `indexOf`, etc.) take into account the value of an array's `length` property when they're called.
    Other methods (e.g., `push`, `splice`, etc.) also result in updates to an array's `length` property.

>```
> var fruits = [];
> fruits.push('banana', 'apple', 'peach');
> 
> console.log(fruits.length); // 3
>```

When setting a property on a JavaScript array when the property is a valid array index and that index is outside the current bounds of the array, the engine will update the array's length property accordingly:

>```
> fruits[5] = 'mango';
> console.log(fruits[5]); // 'mango'
> console.log(Object.keys(fruits));  // ['0', '1', '2', '5']
> console.log(fruits.length); // 6
>```

Increasing the `length`. 

>```
> fruits.length = 10;
> console.log(Object.keys(fruits)); // ['0', '1', '2', '5']
> console.log(fruits.length); // 10
>```

Decreasing the `length` property does, however, delete elements.

>```
> fruits.length = 2;
> console.log(Object.keys(fruits)); // ['0', '1']
> console.log(fruits.length); // 2
>```

 This is explained further on the `Array.length`.

Creating an array using the result of a match
 
 The result of a match between a regular expression and a string can create a JavaScript array.
 This array has properties and elements which provide information about the match.
 Such an array is returned by `RegExp.exec`, `String.match`, and `String.replace`.
 
 To help explain these properties and elements, look at the following example and then refer to the table below:
 
>```
> // Match one d followed by one or more b's followed by one d
> // Remember matched b's and the following d
> // Ignore case
> 
> var myRe = /d(b+)(d)/i;
> var myArray = myRe.exec('cdbBdbsbz');
>```

 The properties and elements returned from this match are as follows:

|   Property/Element    |   Description                     |   Example         |
|  :-----------------:  | --------------------------------- |  ---------------- |
|   `input`             |   A read-only property that reflects the original string against which the regular expression was matched.    |   cdbBdbsbz       |
|   `index`             |   A read-only property that is the zero-based index of the match in the string.   |   1       |
|   `[0]`               |   A read-only element that specifies the last matched characters. |   dbBd       |
|   `[1], ...[n]`       |   Read-only elements that specify the parenthesized substring matches, if included in the regular expression. The number of possible parenthesized substrings is unlimited.   |   [1]: bB         |
|                       |                                    |   [2]: d      |

**_Properties_**

**`Array.length`**

        The Array constructor's length property whose value is 1.

**`get Array[@@species]`**

        The constructor function that is used to create derived objects.
        
**`Array.prototype`**

        Allows the addition of properties to all array objects.
        
        
**_Methods_**

**`Array.from()`**

        Creates a new Array instance from an array-like or iterable object.
        
**`Array.isArray()`**

        Returns true if a variable is an array, if not false.
        
**`Array.of()`**

        Creates a new Array instance with a variable number of arguments, regardless of number or type of the arguments. 


**_`Array` instances_**

        All `Array` instances inherit from `Array.prototype`.  
        The prototype object of the `Array` constructor can be modified to affect all `Array` instances.

**Properties**

**`Array.prototype.constructor`**

        Specifies the function that creates an object's prototype.


**`Array.prototype.length`**

        Reflects the number of elements in an array.


**`Array.prototype[@@unscopables]`**

        A symbol containing property names to exclude from a with binding scope. 

**Methods**

**_Mutator methods_**

These methods modify the array:

**`Array.prototype.copyWithin()`**
        
        Copies a sequence of array elements within the array.
    
**`Array.prototype.fill()`**

        Fills all the elements of an array from a start index to an end index with a static value.
    
**`Array.prototype.pop()`**

        Removes the last element from an array and returns that element.
    
**`Array.prototype.push()`**

        Adds one or more elements to the end of an array and returns the new length of the array.
    
**`Array.prototype.reverse()`**
    
        Reverses the order of the elements of an array in place — the first becomes the last, and the last becomes the first.
    
**`Array.prototype.shift()`**
    
        Removes the first element from an array and returns that element.
    
**`Array.prototype.sort()`**

        Sorts the elements of an array in place and returns the array.
    
**`Array.prototype.splice()`**

        Adds and/or removes elements from an array.
    
**`Array.prototype.unshift()`**

        Adds one or more elements to the front of an array and returns the new length of the array. 


**_Accessor methods_**

These methods do not modify the array and return some representation of the array.

**`Array.prototype.concat()`**
    
        Returns a new array comprised of this array joined with other array(s) and/or value(s).
    
**`Array.prototype.includes()`**

        Determines whether an array contains a certain element, returning true or false as appropriate.
    
**`Array.prototype.indexOf()`**

        Returns the first (least) index of an element within the array equal to the specified value, or -1 if none is found.
    
**`Array.prototype.join()`**

        Joins all elements of an array into a string.
    
**`Array.prototype.lastIndexOf()`**

        Returns the last (greatest) index of an element within the array equal to the specified value, or -1 if none is found.
    
**`Array.prototype.slice()`**

        Extracts a section of an array and returns a new array.
    
**`Array.prototype.toString()`**

        Returns a string representing the array and its elements. Overrides the Object.prototype.toString() method.
    
**`Array.prototype.toLocaleString()`**

        Returns a localized string representing the array and its elements. Overrides the Object.prototype.toLocaleString() method. 


**_Iteration methods_**

    Several methods take as arguments functions to be called back while processing the array. 
    When these methods are called, the length of the array is sampled, and any element added beyond this length from within the callback is not visited. 
    
    Other changes to the array (setting the value of or deleting an element) may affect the results of the operation if the method visits the changed element afterwards. 
    
    While the specific behavior of these methods in such cases is well-defined, you should not rely upon it so as not to confuse others who might read your code. 
    If you must mutate the array, copy into a new array instead.

    
**`Array.prototype.entries()`**
        
        Returns a new Array Iterator object that contains the key/value pairs for each index in the array.
        
**`Array.prototype.every()`**
    
        Returns true if every element in this array satisfies the provided testing function.
        
**`Array.prototype.filter()`**

        Creates a new array with all of the elements of this array for which the provided filtering function returns true.
        
**`Array.prototype.find()`**
        
        Returns the found value in the array, if an element in the array satisfies the provided testing function or undefined if not found.
        
**`Array.prototype.findIndex()`**

        Returns the found index in the array, if an element in the array satisfies the provided testing function or -1 if not found.
        
**`Array.prototype.forEach()`**

        Calls a function for each element in the array.
        
**`Array.prototype.keys()`**

        Returns a new Array Iterator that contains the keys for each index in the array.
    
**`Array.prototype.map()`**

        Creates a new array with the results of calling a provided function on every element in this array.
    
**`Array.prototype.reduce()`**

        Apply a function against an accumulator and each value of the array (from left-to-right) as to reduce it to a single value.
    
**`Array.prototype.reduceRight()`**

        Apply a function against an accumulator and each value of the array (from right-to-left) as to reduce it to a single value.
    
**`Array.prototype.some()`**

        Returns true if at least one element in this array satisfies the provided testing function.
    
**`Array.prototype.values()`**

        Returns a new Array Iterator object that contains the values for each index in the array.
    
**`Array.prototype[@@iterator]()`**

        Returns a new Array Iterator object that contains the values for each index in the array. 



**_Examples_**

**Creating an array**
    The following example creates an array, `msgArray`, with a length of 0, then assigns values to `msgArray[0]` and `msgArray[99]`, changing the length of the array to 100.

>```
> var msgArray = [];
> msgArray[0] = 'Hello';
> msgArray[99] = 'world';
>
> if (msgArray.length === 100) {
>   console.log('The length is 100.');
> }
>```


**Creating a two-dimensional array**
    The following creates a chess board as a two dimensional array of strings.
    The first move is made by copying the 'p' in (6,4) to (4,4).
    The old position (6,4) is made blank.
    
>```
> var board = [ 
>   ['R','N','B','Q','K','B','N','R'],
>   ['P','P','P','P','P','P','P','P'],
>   [' ',' ',' ',' ',' ',' ',' ',' '],
>   [' ',' ',' ',' ',' ',' ',' ',' '],
>   [' ',' ',' ',' ',' ',' ',' ',' '],
>   [' ',' ',' ',' ',' ',' ',' ',' '],
>   ['p','p','p','p','p','p','p','p'],
>   ['r','n','b','q','k','b','n','r'] ];
>
> console.log(board.join('\n') + '\n\n');
> 
> // Move King's Pawn forward 2
> board[4][4] = board[6][4];
> board[6][4] = ' ';
> console.log(board.join('\n'));
>```

Here is the output:

>```
> R,N,B,Q,K,B,N,R
> P,P,P,P,P,P,P,P
>  , , , , , , , 
>  , , , , , , , 
>  , , , , , , , 
>  , , , , , , , 
> p,p,p,p,p,p,p,p
> r,n,b,q,k,b,n,r
>
> R,N,B,Q,K,B,N,R
> P,P,P,P,P,P,P,P
>  , , , , , , , 
>  , , , , , , , 
>  , , , ,p, , , 
>  , , , , , , , 
> p,p,p,p, ,p,p,p
> r,n,b,q,k,b,n,r
>```


**Using an array to tabulate a set of values**

>```
> values = [];
> for (var x = 0; x < 10; x++){
>  values.push([
>   2 ** x,
>   2 * x ** 2
>  ])
> };
> console.table(values)
>```

Results in
(First column is the (index))

>```
> 0	    1	      0
> 1	    2	      2
> 2	    4	      8
> 3	    8	      18
> 4	    16	     32
> 5	    32	     50
> 6	    64         72
> 7	    128	    98
> 8	    256	    128
> 9	    512	    162
>```

----------------------------------------------

### Math

`Math` is an object with arithmetic functions to perform mathematical tasks, it has properties and methods for mathematical constants and functions. Not a function object.
 
Unlike the other global objects, `Math` is not a constructor. 
All properties/methods of `Math` are static and can be called by using Math as an object, without creating it.

You refer to the constant pi as `Math.PI` and you call the sine function as `Math.sin(x)`, where `x` is the method's argument.

Constants are defined with the full precision of real numbers in JavaScript.


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


**_Properties_**

**`Math.E`**

        Euler's constant and the base of natural logarithms, approximately 2.718.
    
**`Math.LN2`**

        Natural logarithm of 2, approximately 0.693.
    
**`Math.LN10`**

        Natural logarithm of 10, approximately 2.303.
    
**`Math.LOG2E`**

        Base 2 logarithm of E, approximately 1.443.

**`Math.LOG10E`**

        Base 10 logarithm of E, approximately 0.434.

**`Math.PI`**

        Ratio of the circumference of a circle to its diameter, approximately 3.14159.

**`Math.SQRT1_2`**

        Square root of 1/2; equivalently, 1 over the square root of 2, approximately 0.707.

**`Math.SQRT2`**

        Square root of 2, approximately 1.414.
    

**_Methods_**


**`Math.abs(x)`**

        Returns the absolute value of a number.

**`Math.acos(x)`**

        Returns the arccosine of a number.

**`Math.acosh(x)`**

        Returns the hyperbolic arccosine of a number.

**`Math.asin(x)`**

        Returns the arcsine of a number.

**`Math.asinh(x)`**

        Returns the hyperbolic arcsine of a number.

**`Math.atan(x)`**

        Returns the arctangent of a number.

**`Math.atanh(x)`**

        Returns the hyperbolic arctangent of a number.

**`Math.atan2(y, x)`**

        Returns the arctangent of the quotient of its arguments.

**`Math.cbrt(x)`**

        Returns the cube root of a number.

**`Math.ceil(x)`**

        Returns the smallest integer greater than or equal to a number.

**`Math.clz32(x)`**

        Returns the number of leading zeroes of a 32-bit integer.

**`Math.cos(x)`**

        Returns the cosine of a number.

**`Math.cosh(x)`**

        Returns the hyperbolic cosine of a number.

**`Math.exp(x)`**

        Returns Ex, where x is the argument, and E is Euler's constant (2.718…), the base of the natural logarithm.

**`Math.expm1(x)`**

        Returns subtracting 1 from exp(x).

**`Math.floor(x)`**

        Returns the largest integer less than or equal to a number.

**`Math.fround(x)`**

        Returns the nearest single precision float representation of a number.

**`Math.hypot([x[, y[, …]]])`**

        Returns the square root of the sum of squares of its arguments.

**`Math.imul(x, y)`**

        Returns the result of a 32-bit integer multiplication.

**`Math.log(x)`**

        Returns the natural logarithm (loge, also ln) of a number.

**`Math.log1p(x)`**

        Returns the natural logarithm (loge, also ln) of 1 + x for a number x.
    
**`Math.log10(x)`**

        Returns the base 10 logarithm of a number.
    
**`Math.log2(x)`**

        Returns the base 2 logarithm of a number.
    
**`Math.max([x[, y[, …]]])`**

        Returns the largest of zero or more numbers.
    
**`Math.min([x[, y[, …]]])`**

        Returns the smallest of zero or more numbers.
    
**`Math.pow(x, y)`**

        Returns base to the exponent power, that is, baseexponent.
    
**`Math.random()`**

        Returns a pseudo-random number between 0 and 1.
    
**`Math.round(x)`**

        Returns the value of a number rounded to the nearest integer.
    
**`Math.sign(x)`**

        Returns the sign of the x, indicating whether x is positive, negative or zero.
    
**`Math.sin(x)`**

        Returns the sine of a number.
    
**`Math.sinh(x)`**

        Returns the hyperbolic sine of a number.
    
**`Math.sqrt(x)`**

        Returns the positive square root of a number.
    
**`Math.tan(x)`**

        Returns the tangent of a number.
    
**`Math.tanh(x)`**

        Returns the hyperbolic tangent of a number.
    
**`Math.trunc(x)`**

        Returns the integral part of the number x, removing any fractional digits. 

### Date
 Work with dates and times in JavaScript.   
 by Date constructor so you can parsing, managing, and displaying dates.
 
 Creates a JavaScript **`Date`** instance that represents a single moment in time. 
 `Date` objects are based on a time value that is the number of milliseconds since 1 January, 1970 UTC.
 
- If no arguments are provided, the constructor creates a JavaScript `Date` object for the current date and time according to system settings.
 
- If at least two arguments are supplied, missing arguments are either set to 1 (if day is missing) or 0 for all others.

- The JavaScript date is based on a time value that is milliseconds since midnight 01 January, 1970 UTC. A day holds 86,400,000 milliseconds. The JavaScript `Date` object range is -100,000,000 days to 100,000,000 days relative to 01 January, 1970 UTC.

- The JavaScript `Date` object provides uniform behavior across platforms. The time value can be passed between systems to create a date that represents the same moment in time.
 
- The JavaScript `Date` object supports a number of UTC (universal) methods, as well as local time methods. 
UTC, also known as Greenwich Mean Time (GMT), refers to the time as set by the World Time Standard.
The local time is the time known to the computer where JavaScript is executed.

- Invoking JavaScript `Date` as a function (i.e., without the `new` operator) will return a string representing the current date and time.


**_Syntax_**

>```
> new Date();
> new Date(value);
> new Date(dateString);
> new Date(year, month, date, hours, minutes, seconds, milliseconds);
>```

**_Parameters_**

**`value`**

        Integer value representing the number of milliseconds since 1 January 1970 00:00:00 UTC, with leap seconds ignored (Unix Epoch; but consider that most Unix time stamp functions count in seconds).
        
**`dateString`**
        
        String value representing a date. The string should be in a format recognized by the Date.parse() method (IETF-compliant RFC 2822 timestamps and also a version of ISO8601). 

**`year`**

        Integer value representing the year. Values from 0 to 99 map to the years 1900 to 1999.

**`month`**

        Integer value representing the month, beginning with 0 for January to 11 for December.

**`date`**

        Optional. Integer value representing the day of the month.
    
**`hours`**

        Optional. Integer value representing the hour of the day.
    
**`minutes`**

        Optional. Integer value representing the minute segment of a time.
    
**`seconds`**

        Optional. Integer value representing the second segment of a time.
    
**`milliseconds`**

        Optional. Integer value representing the millisecond segment of a time.

**_Properties_**

**`Date.prototype`**
    
        Allows the addition of properties to a JavaScript Date object.

**`Date.length`**
    
        The value of Date.length is 7. This is the number of arguments handled by the constructor.


**_Methods_**

**`Date.now()`**
    
        Returns the numeric value corresponding to the current time - the number of milliseconds elapsed since 1 January 1970 00:00:00 UTC, with leap seconds ignored.
    
**`Date.parse()`**
    
        Parses a string representation of a date and returns the number of milliseconds since 1 January, 1970, 00:00:00, UTC, with leap seconds ignored. 

**`Date.UTC()`**
    
        Accepts the same parameters as the longest form of the constructor (i.e. 2 to 7) and returns the number of milliseconds since 1 January, 1970, 00:00:00 UTC, with leap seconds ignored


JavaScript `Date` instances

    All Date instances inherit from Date.prototype. The prototype object of the Date constructor can be modified to affect all Date instances.

**Date.prototype** Methods

**Getter**

**`Date.prototype.getDate()`**

        Returns the day of the month (1-31) for the specified date according to local time.
    
**`Date.prototype.getDay()`**
    
        Returns the day of the week (0-6) for the specified date according to local time.
    
**`Date.prototype.getFullYear()`**
    
        Returns the year (4 digits for 4-digit years) of the specified date according to local time.
    
**`Date.prototype.getHours()`**
    
        Returns the hour (0-23) in the specified date according to local time.
    
**`Date.prototype.getMilliseconds()`**
    
        Returns the milliseconds (0-999) in the specified date according to local time.
    
**`Date.prototype.getMinutes()`**
    
        Returns the minutes (0-59) in the specified date according to local time.
    
**`Date.prototype.getMonth()`**
    
        Returns the month (0-11) in the specified date according to local time.
    
**`Date.prototype.getSeconds()`**
    
        Returns the seconds (0-59) in the specified date according to local time.
    
**`Date.prototype.getTime()`**
    
        Returns the numeric value of the specified date as the number of milliseconds since January 1, 1970, 00:00:00 UTC (negative for prior times).
    
**`Date.prototype.getTimezoneOffset()`**
    
        Returns the time-zone offset in minutes for the current locale.
    
**`Date.prototype.getUTCDate()`**
    
        Returns the day (date) of the month (1-31) in the specified date according to universal time.
    
**`Date.prototype.getUTCDay()`**
    
        Returns the day of the week (0-6) in the specified date according to universal time.
    
**`Date.prototype.getUTCFullYear()`**
    
        Returns the year (4 digits for 4-digit years) in the specified date according to universal time.
    
**`Date.prototype.getUTCHours()`**
    
        Returns the hours (0-23) in the specified date according to universal time.
    
**`Date.prototype.getUTCMilliseconds()`**
    
        Returns the milliseconds (0-999) in the specified date according to universal time.
    
**`Date.prototype.getUTCMinutes()`**

        Returns the minutes (0-59) in the specified date according to universal time.
    
**`Date.prototype.getUTCMonth()`**
    
        Returns the month (0-11) in the specified date according to universal time.
    
**`Date.prototype.getUTCSeconds()`**
    
        Returns the seconds (0-59) in the specified date according to universal time.
    
**`Date.prototype.getYear()`**
    
        Returns the year (usually 2-3 digits) in the specified date according to local time. Use getFullYear() instead.


**Setter**


**`Date.prototype.setDate()`**

        Sets the day of the month for a specified date according to local time.
    
**`Date.prototype.setFullYear()`**

        Sets the full year (e.g. 4 digits for 4-digit years) for a specified date according to local time.
    
**`Date.prototype.setHours()`**

        Sets the hours for a specified date according to local time.
    
**`Date.prototype.setMilliseconds()`**

        Sets the milliseconds for a specified date according to local time.

**`Date.prototype.setMinutes()`**

        Sets the minutes for a specified date according to local time.
    
**`Date.prototype.setMonth()`**

        Sets the month for a specified date according to local time.
    
**`Date.prototype.setSeconds()`**

        Sets the seconds for a specified date according to local time.
    
**`Date.prototype.setTime()`**

        Sets the Date object to the time represented by a number of milliseconds since January 1, 1970, 00:00:00 UTC, allowing for negative numbers for times prior.
    
**`Date.prototype.setUTCDate()`**

        Sets the day of the month for a specified date according to universal time.
    
**`Date.prototype.setUTCFullYear()`**

        Sets the full year (e.g. 4 digits for 4-digit years) for a specified date according to universal time.
    
**`Date.prototype.setUTCHours()`**

        Sets the hour for a specified date according to universal time.
    
**`Date.prototype.setUTCMilliseconds()`**

        Sets the milliseconds for a specified date according to universal time.
    
**`Date.prototype.setUTCMinutes()`**

        Sets the minutes for a specified date according to universal time.
    
**`Date.prototype.setUTCMonth()`**

        Sets the month for a specified date according to universal time.
    
**`Date.prototype.setUTCSeconds()`**

        Sets the seconds for a specified date according to universal time.
    
**`Date.prototype.setYear()`**

        Sets the year (usually 2-3 digits) for a specified date according to local time. Use setFullYear() instead.
    

**Conversion getter**


**`Date.prototype.toDateString()`**

        Returns the "date" portion of the Date as a human-readable string.
    
**`Date.prototype.toISOString()`**

        Converts a date to a string following the ISO 8601 Extended Format.
    
**`Date.prototype.toJSON()`**

        Returns a string representing the Date using toISOString(). Intended for use by JSON.stringify().
    
**`Date.prototype.toGMTString()`**

        Returns a string representing the Date based on the GMT (UT) time zone. Use toUTCString() instead.
    
**`Date.prototype.toLocaleDateString()`**

        Returns a string with a locality sensitive representation of the date portion of this date based on system settings.
    
**`Date.prototype.toLocaleString()`**

        Returns a string with a locality sensitive representation of this date. Overrides the Object.prototype.toLocaleString() method.
    
**`Date.prototype.toLocaleTimeString()`**

        Returns a string with a locality sensitive representation of the time portion of this date based on system settings.
    
**`Date.prototype.toString()`**

        Returns a string representing the specified Date object. 
        Overrides the Object.prototype.toString() method.
    
**`Date.prototype.toTimeString()`**

        Returns the "time" portion of the Date as a human-readable string.
    
**`Date.prototype.toUTCString()`**

        Converts a date to a string using the UTC timezone.
    
**`Date.prototype.valueOf()`**

        Returns the primitive value of a Date object. Overrides the Object.prototype.valueOf() method. 


** Examples **

**Several ways to create a `Date` object**

The following examples show several ways to create JavaScript dates:

>```
> var today = new Date();
> var birthday = new Date('December 17, 1995 03:24:00');
> var birthday = new Date('1995-12-17T03:24:00');
> var birthday = new Date(1995, 11, 17);
> var birthday = new Date(1995, 11, 17, 3, 24, 0);
>```


**Two digit years map to 1900 - 1999**

In order to create and get dates between the years 0 and 99 the `Date.prototype.setFullYear()` and `Date.prototype.getFullYear()` methods should be used.

>```
> var date = new Date(98, 1); // Sun Feb 01 1998 00:00:00 GMT+0000 (GMT)
> 
> // Deprecated method, 98 maps to 1998 here as well
> date.setYear(98);           // Sun Feb 01 1998 00:00:00 GMT+0000 (GMT)
> 
> date.setFullYear(98);       // Sat Feb 01 0098 00:00:00 GMT+0000 (BST)
>```


**Calculating elapsed time**

The following examples show how to determine the elapsed time between two JavaScript dates in milliseconds.

Due to the differing lengths of days (due to daylight saving changeover), months and years, expressing elapsed time in units greater than hours, minutes and seconds requires addressing a number of issues and should be thoroughly researched before being attempted.

>```
> // using Date objects
> var start = Date.now();
> 
> // the event to time goes here:
> doSomethingForALongTime();
> var end = Date.now();
> var elapsed = end - start; // elapsed time in milliseconds
>```

>```
> // using built-in methods
> var start = new Date();
>
> // the event to time goes here:
> doSomethingForALongTime();
> var end = new Date();
> var elapsed = end.getTime() - start.getTime(); // elapsed time in milliseconds
>```

>```
> // to test a function and get back its return
> function printElapsedTime(fTest) {
>   var nStartTime = Date.now(),
>       vReturn = fTest(),
>       nEndTime = Date.now();
> 
>   console.log('Elapsed time: ' + String(nEndTime - nStartTime) + ' milliseconds');
>   return vReturn;
> }
> 
> var yourFunctionReturn = printElapsedTime(yourFunction);
>```

#### The Date Constructor

There are four ways of invoking the constructor of `Date`


### Error

The __`Error`__ constructor creates an error object.  
Instances of `Error` objects are thrown when runtime errors occur.  
The `Error` object can also be used as a base object for user-defined exceptions.   
See below for standard built-in error types.

Runtime errors result in new `Error` objects being created and thrown.

This page documents the use of the `Error` object itself and its use as a constructor function. 
For a list of properties and methods inherited by `Error` instances, see `Error.prototype`.

    
**Error types**

Besides the generic `Error` constructor, there are seven other core error constructors in JavaScript. For client-side exceptions, see `Exception Handling Statements`.

**`EvalError`**
    
        Creates an instance representing an error that occurs regarding the global function `eval()`.
    
**`InternalError`**
    
        Creates an instance representing an error that occurs when an internal error in the JavaScript engine is thrown. E.g. "too much recursion".
    
**`RangeError`**
    
        Creates an instance representing an error that occurs when a numeric variable or parameter is outside of its valid range.
    
**`ReferenceError`**
    
        Creates an instance representing an error that occurs when de-referencing an invalid reference.
    
**`SyntaxError`**
    
        Creates an instance representing a syntax error that occurs while parsing code in eval().
    
**`TypeError`**
    
        Creates an instance representing an error that occurs when a variable or parameter is not of a valid type.
    
**`URIError`**
    
        Creates an instance representing an error that occurs when encodeURI() or decodeURI() are passed invalid parameters. 


**Properties**

**`Error.prototype`**
    
        Allows the addition of properties to `Error` instances. 



**Methods**

The global `Error` object contains no methods of its own, however, it does inherit some methods through the prototype chain.



**Error instances**

All `Error` instances and instances of non-generic errors inherit from `Error.prototype`.  
As with all constructor functions, you can use the prototype of the constructor to add properties or methods to all instances created with that constructor.


**Properties**

**Standard properties**


**`Error.prototype.constructor`**
    
        Specifies the function that created an instance's prototype.
    
**`Error.prototype.message`**
    
        Error message.
    
**`Error.prototype.name`**
    
        Error name.
        
        
**Methods**

**`Error.prototype.toSource()`**

    Returns a string containing the source of the specified `Error` object; you can use this value to create a new object. Overrides the `Object.prototype.toSource()` method.

**`Error.prototype.toString()`**

    Returns a string representing the specified object. 
    Overrides the `Object.prototype.toString()` method. 


**Examples**

* **Throwing a generic error**

Usually you create an `Error` object with the intention of raising it using the `throw` keyword.  
You can handle the error using the `try...catch` construct:

>```
> try {
>   throw new Error('Whoops!');
> } catch (e) {
>   console.log(e.name + ': ' + e.message);
> }
>```


**Handling a specific error**

You can choose to handle only specific error types by testing the error type with the error's `constructor` property or, if you're writing for modern JavaScript engines, instanceof keyword:

>```
> try {
>   foo.bar();
> } catch (e) {
>   if (e instanceof EvalError) {
>     console.log(e.name + ': ' + e.message);
>   } else if (e instanceof RangeError) {
>     console.log(e.name + ': ' + e.message);
>   }
>   // ... etc
> }
>```


**Custom Error Types**

You might want to define your own error types deriving from `Error` to be able to `throw new MyError()` and use `instanceof MyError` to check the kind of error in the exception handler.  
This results in cleaner and more consistent error handling code.  
See "What's a good way to extend Error in JavaScript?" on StackOverflow for an in-depth discussion.

**ES6 Custom Error Class**

>```
> class CustomError extends Error {
>   constructor(foo = 'bar', ...params) {
>     // Pass remaining arguments (including vendor specific ones) to parent constructor
>     super(...params);
> 
>     // Maintains proper stack trace for where our error was thrown (only available on V8)
>     if (Error.captureStackTrace) {
>       Error.captureStackTrace(this, CustomError);
>     }
> 
>     // Custom debugging information
>     this.foo = foo;
>     this.date = new Date();
>   }
> }
> 
> try {
>   throw new CustomError('baz', 'bazMessage');
> } catch(e){
>   console.log(e.foo); //baz
>   console.log(e.message); //bazMessage
>   console.log(e.stack); //stacktrace
> }
>```

**ES5 Custom Error Object**

>```
> function CustomError(foo, message, fileName, lineNumber) {
>   var instance = new Error(message, fileName, lineNumber);
>   instance.foo = foo;
>   Object.setPrototypeOf(instance, Object.getPrototypeOf(this));
>   if (Error.captureStackTrace) {
>     Error.captureStackTrace(instance, CustomError);
>   }
>   return instance;
> }
> 
> CustomError.prototype = Object.create(Error.prototype, {
>   constructor: {
>     value: Error,
>     enumerable: false,
>     writable: true,
>     configurable: true
>   }
> });
> 
> if (Object.setPrototypeOf){
>   Object.setPrototypeOf(CustomError, Error);
> } else {
>   CustomError.__proto__ = Error;
> }
> 
> 
> try {
>   throw new CustomError('baz', 'bazMessage');
> } catch(e){
>   console.log(e.foo); //baz
>   console.log(e.message) ;//bazMessage
> }
>```


### Boolean

The value passed as the first parameter is converted to a boolean value, if necessary. If the value is omitted or is `0`, `-0`, `null`, `false`, `NaN`, `undefined`, or the empty string (`""`), the object has an initial value of `false`. If the DOM object `document.all` is passed as a parameter, the new boolean object also has an initial value of `false`. All other values, including any object or the string `"false"`, create an object with an initial value of `true`.

Do not confuse the primitive `Boolean` values `true` and `false` with the true and false values of the `Boolean` object.

Any object of which the value is not `undefined` or `null`, including a `Boolean` object whose value is `false`, evaluates to `true` when passed to a conditional statement. For example, the condition in the following `if` statement evaluates to `true`:

>```
> var x = new Boolean(false);
> if (x) {
>   // this code is executed
> }
>```

This behavior does not apply to `Boolean` primitives. For example, the condition in the following `if` statement evaluates to `false`:

>```
> var x = false;
> if (x) {
>   // this code is not executed
> }
>```

Do not use a `Boolean` object to convert a non-boolean value to a boolean value. Instead, use `Boolean` as a function to perform this task:

var x = Boolean(expression);     // preferred
var x = new Boolean(expression); // don't use

If you specify any object, including a `Boolean` object whose value is `false`, as the initial value of a `Boolean` object, the new `Boolean` object has a value of `true`.

>```
> var myFalse = new Boolean(false);   // initial value of false
> var g = new Boolean(myFalse);       // initial value of true
> var myString = new String('Hello'); // string object
> var s = new Boolean(myString);      // initial value of true
>```

Do not use a `Boolean` object in place of a `Boolean` primitive.


**Syntax**

>```
> new Boolean([value])
>```

**Parameters**

**`value`**

        Optional. The initial value of the Boolean object. 


**Properties**

**`Boolean.length`**

 Length property whose value is 1.

**`Boolean.prototype`**
    
 Represents the prototype for the `Boolean` constructor. 
    

**Methods**

While the global `Boolean` object contains no methods of its own, it does inherit some methods through the prototype chain:


**`Boolean` instances**

All `Boolean` instances inherit from `Boolean.prototype`.  
As with all constructors, the prototype object dictates instances' inherited properties and methods.


**Properties**

**`Boolean.prototype.constructor`**

Returns the function that created an instance's prototype.  This is the `Boolean` function by default. 
    
    
**Methods**

**`Boolean.prototype.toSource()`**

 Returns a string containing the source of the `Boolean` object.  
 Overrides the `Object.prototype.toSource()` method.
        
**`Boolean.prototype.toString()`**
    
 Returns a string of either `"true"` or `"false"` depending upon the value of the object.  
 Overrides the `Object.prototype.toString()` method.
    
**`Boolean.prototype.valueOf()`**
    
 Returns the primitive value of the `Boolean` object.  
 Overrides the `Object.prototype.valueOf()` method.
 
 
**Examples**

* ** Creating `Boolean` objects with an initial value of `false` **

>```
> var bNoParam = Boolean();
> var bZero = Boolean(0);
> var bNull = Boolean(null);
> var bEmptyString = Boolean('');
> var bfalse = Boolean(false);
>```


* ** Creating `Boolean` objects with an initial value of `true` **

>```
> var btrue = Boolean(true);
> var btrueString = Boolean('true');
> var bfalseString = Boolean('false');
> var bSuLin = Boolean('Su Lin');
> var bArrayProto = Boolean([]);
> var bObjProto = Boolean({});
>```


### Symbol

The `Symbol()` function returns a value of type __symbol__, has static properties that expose several members of built-in objects, has static methods that expose the global symbol registry, and resembles a built-in object class but is incomplete as a constructor because it does not support the syntax "`new Symbol()`".  

Every symbol value returned from `Symbol()` is unique.  
A symbol value may be used as an identifier for object properties; this is the data type's only purpose.  
Some further explanation about purpose and usage can be found in the glossary entry for Symbol.

The data type __symbol__ is a primitive data type.

To create a new primitive symbol, you write `Symbol()` with an optional string as its description:

>```
> var sym1 = Symbol();
> var sym2 = Symbol('foo');
> var sym3 = Symbol('foo');
>```

The above code creates three new symbols.  
Note that `Symbol("foo")` does not coerce the string "foo" into a symbol.  
It creates a new symbol each time:

>```
> Symbol('foo') === Symbol('foo'); // false
>```

The following syntax with the `new` operator will throw a `TypeError`:

>```
> var sym = new Symbol(); // TypeError
>```

This prevents authors from creating an explicit `Symbol` wrapper object instead of a new symbol value and might be surprising as creating explicit wrapper objects around primitive data types is generally possible (for example, `new Boolean`, `new String` and `new Number`).

If you really want to create a `Symbol` wrapper object, you can use the `Object()` function:

>```
> var sym = Symbol('foo');
> typeof sym;     // "symbol" 
> var symObj = Object(sym);
> typeof symObj;  // "object"
>```


**Shared symbols in the global symbol registry**

The above syntax using the `Symbol()` function will not create a global symbol that is available in your whole codebase.  
To create symbols available across files and even across realms (each of which has its own global scope), use the methods `Symbol.for()` and `Symbol.keyFor()` to set and retrieve symbols from the global symbol registry.


**Finding symbol properties on objects**

The method `Object.getOwnPropertySymbols()` returns an array of symbols and lets you find symbol properties on a given object.  
Note that every object is initialized with no own symbol properties, so that this array will be empty unless you've set symbol properties on the object.



**Syntax**

>`Symbol([`_description_`])`

**Parameters**

**`description`** _Optional_
    
 Optional, string.  
 A description of the symbol which can be used for debugging but not to access the symbol itself. 
    


**Properties**

**`Symbol.length`**
    
 Length property whose value is 0.
    
**`Symbol.prototype`**
    
 Represents the prototype for the `Symbol` constructor. 
    
**Well-known symbols**

In addition to your own symbols, JavaScript has some built-in symbols which represent internal language behaviors which were not exposed to developers in ECMAScript 5 and before.  
These symbols can be accessed using the following properties:

**Iteration symbols**

**`Symbol.iterator`**
    
 A method returning the default iterator for an object. Used by `for...of`.
    
**`Symbol.asyncIterator`**

 A method that returns the default AsyncIterator for an object. Used by `for await of`. 

**Regular expression symbols**

**`Symbol.match`**
    
 A method that matches against a string, also used to determine if an object may be used as a regular expression.  
 Used by String.prototype.match().
    
**`Symbol.replace`**

 A method that replaces matched substrings of a string. 
 Used by `String.prototype.replace()`.
    
**`Symbol.search`**
    
 A method that returns the index within a string that matches the regular expression.  
 Used by `String.prototype.search()`.
    
**`Symbol.split`**

 A method that splits a string at the indices that match a regular expression.  
 Used by `String.prototype.split()`. 

**Other symbols**

**`Symbol.hasInstance`**
 
 A method determining if a constructor object recognizes an object as its instance.  
 Used by `instanceof`.
    
**`Symbol.isConcatSpreadable`**

 A Boolean value indicating if an object should be flattened to its array elements.  
 Used by `Array.prototype.concat()`.
    
**`Symbol.unscopables`**

 An object value of whose own and inherited property names are excluded from the `with` environment bindings of the associated object.
    
**`Symbol.species`**

 A constructor function that is used to create derived objects.
    
**`Symbol.toPrimitive`**

 A method converting an object to a primitive value.
    
**`Symbol.toStringTag`**

 A string value used for the default description of an object.  
 Used by `Object.prototype.toString()`. 


**Methods**

**`Symbol.for(key)`**

 Searches for existing symbols with the given key and returns it if found.  
 Otherwise a new symbol gets created in the global symbol registry with this key.
    
**`Symbol.keyFor(sym)`**

 Retrieves a shared symbol key from the global symbol registry for the given symbol. 
    

**`Symbol` prototype**

All Symbols inherit from `Symbol.prototype`.

**Properties**

`Symbol.prototype.constructor`

 Returns the function that created an instance's prototype.  
 This is the `Symbol` function by default.


**Methods**

**`Symbol.prototype.toSource()`**

 Returns a string containing the source of the `Symbol` object.  
 Overrides the `Object.prototype.toSource()` method.
    
**`Symbol.prototype.toString()`**

 Returns a string containing the description of the `Symbol`.  
 Overrides the `Object.prototype.toString()` method.
    
**`Symbol.prototype.valueOf()`**

 Returns the primitive value of the `Symbol` object.   Overrides the `Object.prototype.valueOf()` method.
    
**`Symbol.prototype[@@toPrimitive]`**

 Returns the primitive value of the `Symbol` object.


**Examples**

* **Using the typeof operator with symbols**

   The `typeof` operator can help you to identify symbols.

>```
> typeof Symbol() === 'symbol'
> typeof Symbol('foo') === 'symbol'
> typeof Symbol.iterator === 'symbol'
>```

* **Symbol type conversions**

    Some things to note when working with type conversion of symbols.

    When trying to convert a symbol to a number, a `TypeError` will be thrown
    (e.g. `+sym` or `sym | 0`).  
    When using loose equality, `Object(sym) == sym` returns `true`.  
    `Symbol("foo") + "bar"` throws a `TypeError` (can't convert symbol to string). This prevents you from silently creating a new string property name from a symbol, for example.
    The "safer" `String(sym)` conversion works like a call to `Symbol.prototype.toString()` with symbols, but note that `new String(sym)` will throw.  


* **Symbols and `for...in` iteration**

    Symbols are not enumerable in `for...in` iterations.   
    In addition, `Object.getOwnPropertyNames()` will not return symbol object properties,  
    however, you can use `Object.getOwnPropertySymbols()` to get these.

>```
> var obj = {};
> 
> obj[Symbol('a')] = 'a';
> obj[Symbol.for('b')] = 'b';
> obj['c'] = 'c';
> obj.d = 'd';
> 
> 
> for (var i in obj) {
>    console.log(i); // logs "c" and "d"
> }
>```

* **Symbols and `JSON.stringify()`**

    Symbol-keyed properties will be completely ignored when using `JSON.stringify()`:

>```
> JSON.stringify({[Symbol('foo')]: 'foo'});                 
> // '{}'
>```

For more details, see `JSON.stringify()`.

* **Symbol wrapper objects as property keys**

    When a Symbol wrapper object is used as a property key, this object will be coerced to its wrapped symbol:

>```
> var sym = Symbol('foo');
> var obj = {[sym]: 1};
> obj[sym];            // 1
> obj[Object(sym)];    // still 1
>```


## Classes

 JavaScript classes introduced in ECMAScript 2015 are primarily syntactical sugar over JavaScript's existing prototype-based inheritance.
 The class syntax is not introducing a new object-oriented inheritance model to JavaScript. JavaScript classes provide a much simpler and clearer syntax to create objects and deal with inheritance.


### Defining Classes


 Classes are in fact "special functions", and just as you can define function expressions and function declarations, the class syntax has two components: class expressions and class declarations.


**Class declarations**
One way to define a class is using a class declaration
To declare a class, you use the class keyword with the name of the class ("Rectangle" here).
 
>```
>  class Rectangle {
>   constructor(height, width) {
>     this.height = height;
>     this.width = width;
>   }
> }
>```


**Hoisting**
An important difference between __function declarations__ and __class declarations__ is that function declarations are hoisted and class declarations are not.
You first need to declare your class and then access it, otherwise code like the following will throw a ReferenceError:

>```
> var p = new Rectangle(); // ReferenceError
> 
> class Rectangle {}
>```


**Class Expressions**
A class expression is another way to define a class.
Class expressions can be named or unnamed. The name given to a named class expression is local to the class's body.

>```
> // unnamed
> var Rectangle = class {
>   constructor(height, width) {
>     this.height = height;
>     this.width = width;
>   }
> };
>
> // named
> var Rectangle = class Rectangle {
>   constructor(height, width) {
>     this.height = height;
>     this.width = width;
>   }
> };
>```

Note: Class __expressions__ also suffer from the same hoisting issues mentioned for Class __declarations__.


### Class Body and Method Definitions

 The body of a class is the part that is in curly brackets {}. 
 This is where you define class members, such as methods or constructor.


** Strict mode **

The bodies of _class declarations_ and _class expressions_ are executed in strict mode i.e. constructor, static and prototype methods, getter and setter functions are executed in strict mode.

** Constructor **

The constructor method is a special method for creating and initializing an object created with a class.

There can only be one special method with the name "constructor" in a class.
A SyntaxError will be thrown if the class contains more than one occurrence of a constructor method.

A constructor can use the super keyword to call the constructor of a parent class.


** Prototype methods **

>```
> class Rectangle {
>   constructor(height, width) {
>     this.height = height;
>     this.width = width;
>   }
>   
>     get area() {
>     return this.calcArea();
>   }
> 
>   calcArea() {
>     return this.height * this.width;
>   }
> }
> 
> const square = new Rectangle(10, 10);
> 
> console.log(square.area);
>```


** Static methods **

The `static` keyword defines a static method for a class. 
Static methods are called without instantiating their class and __cannot__ be called through a class instance.
Static methods are often used to create utility functions for an application.

>```
> class Point {
>   constructor(x, y) {
>     this.x = x;
>     this.y = y;
>   }
> 
>   static distance(a, b) {
>     const dx = a.x - b.x;
>     const dy = a.y - b.y;
> 
>     return Math.hypot(dx, dy);
>   }
> }
> 
> const p1 = new Point(5, 5);
> const p2 = new Point(10, 10);
> 
> console.log(Point.distance(p1, p2));
>```


** Boxing with prototype and static methods **

When a static or prototype method is called without an object valued "this", then the "this" value will be __undefined__ inside the called function. Autoboxing will not happen. The behavior will be the same even if we write the code in non-strict mode because all the functions, methods, constructor, getters or setters are executed in strict mode. 
So if we do not specify `this` value then the this value will be __undefined__.

>```
> class Animal { 
>   speak() {
>     return this;
>   }
>   static eat() {
>     return this;
>   }
> }
>
> let obj = new Animal();
> obj.speak(); // Animal {}
> let speak = obj.speak;
> speak(); // undefined
> 
> Animal.eat() // class Animal
> let eat = Animal.eat;
> eat(); // undefined
>```

If we write the above code using traditional function based classes, then autoboxing will happen based on the "this" value for which the function was called.


>```
> function Animal() { }
> 
> Animal.prototype.speak = function() {
>   return this;
> }
> 
> Animal.eat = function() {
>   return this;
> }
> 
> let obj = new Animal();
> let speak = obj.speak;
> speak(); // global object
> 
> let eat = Animal.eat;
> eat(); // global object
>```


### Sub classing with extends

The `extends` keyword is used in _class declarations_ or _class expressions_ to create a class as a child of another class.

>```
> class Animal { 
>   constructor(name) {
>     this.name = name;
>   }
>   
>   speak() {
>     console.log(this.name + ' makes a noise.');
>   }
> }
> 
> class Dog extends Animal {
>   speak() {
>     console.log(this.name + ' barks.');
>   }
> }
> 
> var d = new Dog('Mitzie');
> d.speak(); // Mitzie barks.
>```

If there is a constructor present in sub-class, it needs to first call super() before using "this".

One may also extend traditional function-based "classes":

>```
> function Animal (name) {
>   this.name = name;  
> }
> 
> Animal.prototype.speak = function () {
>   console.log(this.name + ' makes a noise.');
> }
> 
> class Dog extends Animal {
>   speak() {
>     console.log(this.name + ' barks.');
>   }
> }
> 
> var d = new Dog('Mitzie');
> d.speak(); // Mitzie barks.
> 
>```


Note that classes cannot extend regular (non-constructible) objects.

If you want to inherit from a regular object, you can instead use Object.setPrototypeOf():

>```
> var Animal = {
>   speak() {
>     console.log(this.name + ' makes a noise.');
>   }
> };
> 
> class Dog {
>   constructor(name) {
>     this.name = name;
>   }
> }
> 
> Object.setPrototypeOf(Dog.prototype, Animal);// If you do not do this you will get a TypeError when you invoke speak
> 
> var d = new Dog('Mitzie');
> d.speak(); // Mitzie makes a noise.
>```

### Species

 You might want to return `Array` objects in your derived array class `MyArray`.
 The species pattern lets you override default constructors.
 
 
 For example, when using methods such as map() that returns the default constructor, 
 you want these methods to return a parent `Array` object, instead of the `MyArray` object.
 The `Symbol.species` symbol lets you do this:
 
>```
> class MyArray extends Array {
>   // Overwrite species to the parent Array constructor
>   static get [Symbol.species]() { return Array; }
> }
>
> var a = new MyArray(1,2,3);
> var mapped = a.map(x => x * x);
> 
> console.log(mapped instanceof MyArray); // false
> console.log(mapped instanceof Array);   // true
>```


### Super class calls with **`super`**
 
 The `super` keyword is used to call functions on an object's parent.
 
>```
> class Cat { 
>   constructor(name) {
>     this.name = name;
>   }
>   
>   speak() {
>     console.log(this.name + ' makes a noise.');
>   }
> }
> 
> class Lion extends Cat {
>   speak() {
>     super.speak();
>     console.log(this.name + ' roars.');
>   }
> }
> 
> var l = new Lion('Fuzzy');
> l.speak(); 
> // Fuzzy makes a noise.
> // Fuzzy roars.
>```


### Mix-ins

 Abstract subclasses or `mix-ins` are templates for classes.
 An ECMAScript class can only have a single superclass, so multiple inheritance from tooling classes, for example, is not possible.
 The functionality must be provided by the superclass.
 
 A function with a superclass as input and a subclass extending that superclass as output can be used to implement mix-ins in ECMAScript:
 
>```
> var calculatorMixin = Base => class extends Base {
>   calc() { }
> };
> 
> var randomizerMixin = Base => class extends Base {
>   randomize() { }
> };
>```

A class that uses these mix-ins can then be written like this:

>```
> class Foo { }
> class Bar extends calculatorMixin(randomizerMixin(Foo)) { }
>```


### Class Constructor

 The `constructor` method is a special method for creating and initializing an object created within a `class`.
 
**_Syntax_**

>```
> constructor([arguments]) { ... }
>```

There can be only one special method with the name "constructor" in a class.
Having more than one occurrence of a `constructor` method in a class will throw a `SyntaxError` error.

A `constructor` can use the super keyword to call the constructor of a parent class.

If you do not specify a constructor method, a default constructor is used.


**_Examples_**

Using the constructor method

>```
> class Square extends Polygon {
>   constructor(length) {
>     // Here, it calls the parent class' constructor with lengths
>     // provided for the Polygon's width and height
>     super(length, length);
>     // Note: In derived classes, super() must be called before you
>     // can use 'this'. Leaving this out will cause a reference error.
>     this.name = 'Square';
>   }
> 
>   get area() {
>     return this.height * this.width;
>   }
> 
>   set area(value) {
>     this.area = value;
>   } 
> }
>```

Another example
Take a look at this code snippet

>```
> class Polygon {
>     constructor() {
>         this.name = "Polygon";
>     }
> }
> 
> class Square extends Polygon {
>     constructor() {
>         super();
>     }
> }
> 
> class Rectangle {}
> 
> Object.setPrototypeOf(Square.prototype, Rectangle.prototype);
> 
> console.log(Object.getPrototypeOf(Square.prototype) === Polygon.prototype); //false
> console.log(Object.getPrototypeOf(Square.prototype) === Rectangle.prototype); //true
> 
> let newInstance = new Square();
> console.log(newInstance.name); //Polygon
>```

Here the prototype of __Square__ class is changed but still the constructor of the previous base class __Polygon__ is called when a new instance of a square is being created.


**Default constructors**

As stated, if you do not specify a constructor method a default constructor is used. 
For base classes the default constructor is:

>```
> constructor() {}
>```

For derived classes, the default constructor is:

>```
> constructor(...args) {
>   super(...args);
> }
>```


### Class Extends

The __`extends`__ keyword is used in class declarations or class expressions to create a class which is a child of another class.

>```
> class ChildClass extends ParentClass { ... }
>```

The `extends` keyword can be used to subclass custom classes as well as built-in objects.

The `.prototype` of the extension must be an Object or `null`.


**_Examples_**

Using `extends`

The first example creates a class called `Square` from a class called `Polygon`.

>```
> class Square extends Polygon {
>   constructor(length) {
>     // Here, it calls the parent class' constructor with lengths
>     // provided for the Polygon's width and height
>     super(length, length);
>     // Note: In derived classes, super() must be called before you
>     // can use 'this'. Leaving this out will cause a reference error.
>     this.name = 'Square';
>   }
> 
>   get area() {
>     return this.height * this.width;
>   }
> }
>```


Using `extends` with built-in objects

This example extends the built-in `Date` object.

>```
> class myDate extends Date {
>   constructor() {
>     super();
>   }
> 
>   getFormattedDate() {
>     var months = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
>     return this.getDate() + '-' + months[this.getMonth()] + '-' + this.getFullYear();
>   }
> }
>```


Extending `null`

Extending from `null` works like with a normal class, except that the prototype object does not inherit from `Object.prototype`.

>```
> class nullExtends extends null {
>   constructor() {}
> }
> 
> Object.getPrototypeOf(nullExtends); // Function.prototype
> Object.getPrototypeOf(nullExtends.prototype) // null
> 
> new nullExtends(); //ReferenceError: this is not defined
>```


### Class `static`

Static method calls are made directly on the class and are not callable on instances of the class.
Static methods are often used to create utility functions.


>```
> static methodName() { ... }
>```

**Calling static methods**

** From another static method **

In order to call a static method within another static method of the same class, you can use the `this` keyword.

>```
> class StaticMethodCall {
>   static staticMethod() {
>     return 'Static method has been called';
>   }
>   static anotherStaticMethod() {
>     return this.staticMethod() + ' from another static method';
>   }
> }
> StaticMethodCall.staticMethod(); 
> // 'Static method has been called'
> 
> StaticMethodCall.anotherStaticMethod(); 
> // 'Static method has been called from another static method'
>```

** From class constructor and other methods **

Static methods are not directly accessible using the `this` keyword from non-static methods.
You need to call them using the class name: 
`CLASSNAME.STATIC_METHOD_NAME()` 
or by calling the method as a property of the constructor:
`this.constructor.STATIC_METHOD_NAME()`.

>```
> class StaticMethodCall {
>   constructor() {
>     console.log(StaticMethodCall.staticMethod()); 
>     // 'static method has been called.' 
> 
>     console.log(this.constructor.staticMethod()); 
>     // 'static method has been called.' 
>   }
> 
>   static staticMethod() {
>     return 'static method has been called.';
>   }
> }
>```

**_Examples_**

The following example demonstrates several things:
1. How a static method is implemented on a class.
2. That a class with a static member can be sub-classed.
3. How a static method can and cannot be called.

>```
> class Triple {
>   static triple(n) {
>     if (n === undefined) {
>       n = 1;
>     }
>     return n * 3;
>   }
> }
> 
> class BiggerTriple extends Triple {
>   static triple(n) {
>     return super.triple(n) * super.triple(n);
>   }
> }
> 
> console.log(Triple.triple());        // 3
> console.log(Triple.triple(6));       // 18
> 
> var tp = new Triple();
> 
> console.log(BiggerTriple.triple(3));
> // 81 (not affected by parent's instantiation)
> 
> console.log(tp.triple());
> // 'tp.triple is not a function'.
>```


### WebAssembly

The __`WebAssembly`__ JavaScript object acts as the namespace for all WebAssembly-related functionality.

Unlike most other global objects, WebAssembly is not a constructor (it is not a function object).  
You can compare it to `Math`, which is also a namespace object for mathematical constants and functions, or to `Intl` which is the namespace object for internationalization constructors and other language sensitive functions.

The primary uses for the `WebAssembly` object are:

- Loading WebAssembly code, using the `WebAssembly.instantiate()` function.

- Creating new memory and table instances via the `WebAssembly.Memory()`/`WebAssembly.Table()` constructors.

- Providing facilities to handle errors that occur in WebAssembly via the `WebAssembly.CompileError()`/`WebAssembly.LinkError()`/`WebAssembly.RuntimeError()` constructors.


**Methods**

**`WebAssembly.instantiate()`**

 The primary API for compiling and instantiating WebAssembly code, returning both a `Module` and its first `Instance`.
    
**`WebAssembly.instantiateStreaming()`**

 Compiles and instantiates a WebAssembly module directly from a streamed underlying source, returning both a `Module` and its first `Instance`.
    
**`WebAssembly.compile()`**

 Compiles a `WebAssembly.Module` from WebAssembly binary code, leaving instantiation as a separate step.
    
**`WebAssembly.compileStreaming()`**

 compiles a `ebAssembly.Module` directly from a streamed underlying source, leaving instantiation as a separate step.
    
**`WebAssembly.validate()`**

 Validates a given typed array of WebAssembly binary code, returning whether the bytes are valid WebAssembly code (`true`) or not (`false`). 


**Constructors**

**`WebAssembly.Module()`**

 Creates a new WebAssembly `Module` object.
    
**`WebAssembly.Instance()`**

 Creates a new WebAssembly `Instance` object.
    
**`WebAssembly.Memory()`**

 Creates a new WebAssembly `Memory` object.
    
**`WebAssembly.Table()`**

 Creates a new WebAssembly `Table` object.
    
**`WebAssembly.CompileError()`**

 Creates a new WebAssembly `CompileError` object.
    
**`WebAssembly.LinkError()`**

 Creates a new WebAssembly `LinkError` object.
    
**`WebAssembly.RuntimeError()`**
    
 Creates a new WebAssembly `RuntimeError` object. 


**Examples**

After fetching some WebAssembly bytecode using fetch, we compile and instantiate the module using the `WebAssembly.instantiate()` function, importing a JavaScript function into the WebAssembly Module in the process. This promise resolves to an object (result) containing the compiled `Module` and `Instance` objects.  
We then call an Exported WebAssembly function that is exported by the `Instance`.


>``` 
> var importObject = {
>   imports: {
>     imported_func: function(arg) {
>       console.log(arg);
>     }
>   }
> };
> 
> fetch('simple.wasm').then(response =>
>   response.arrayBuffer()
> ).then(bytes =>
>   WebAssembly.instantiate(bytes, importObject)
> ).then(result =>
>   result.instance.exports.exported_func()
> );
>```

---


## Strict Mode

### ECMAScript 5's strict mode 

ECMAScript 5's strict mode is a way to _`opt in`_ to a restricted variant of JavaScript. Strict mode isn't just a subset: it _intentionally_ has different semantics from normal code. 

Browsers not supporting strict mode will run strict mode code with different behavior from browsers that do, so don't rely on strict mode without feature-testing for support for the relevant aspects of strict mode.

Strict mode code and non-strict mode code can coexist, so scripts can opt into strict mode incrementally.


Strict mode makes several changes to normal JavaScript semantics.
 First, strict mode eliminates some JavaScript silent errors by changing them to throw errors.

 Second, strict mode fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode code can sometimes be made to run faster than identical code that's not strict mode.
 
 Third, strict mode prohibits some syntax likely to be defined in future versions of ECMAScript.
 
*Sometimes, you'll see the default, non-strict, mode referred to as "sloppy mode". This isn't an official term, but be aware of it, just in case.*


### Invoking Strict Mode

 Strict mode applies to _entire scripts_ or to _individual functions_.
 It doesn't apply to block statements enclosed in {} braces; attempting to apply it to such contexts does nothing.
 `eval` code, Function code, event handler attributes, strings passed to `WindowTimers.setTimeout()`, and the like are entire scripts, and invoking strict mode in them works as expected.
 
 
#### Strict Mode for Scripts

 To invoke strict mode for an entire script, put the _exact_ statement "use strict"; (or 'use strict';) before any other statements.
 
>```
> // Whole-script strict mode syntax
> 'use strict';
> var v = "Hi! I'm a strict mode script!";
>```

This syntax has a trap that has already bitten a major site: it isn't possible to blindly concatenate non-conflicting scripts. Consider concatenating a strict mode script with a non-strict mode script: the entire concatenation looks strict! The inverse is also true: non-strict plus strict looks non-strict. Concatenation of strict mode scripts with each other is fine, and concatenation of non-strict mode scripts is fine.
Only concatenating strict and non-strict scripts is problematic. It is thus recommended that you enable strict mode on a function-by-function basis (at least during the transition period).

You can also take the approach of wrapping the entire contents of a script in a function and having that outer function use strict mode. This eliminates the concatenation problem but it means that you have to explicitly export any global variables out of the function scope.


#### Strict Mode for Functions

Likewise, to invoke strict mode for a function, put the _exact_ statement `"use strict";` (or `'use strict';`) in the function's body before any other statements.

>```
> function strict() {
>   // Function-level strict mode syntax
>   'use strict';
>   function nested() { return 'And so am I!'; }
>   return "Hi!  I'm a strict mode function!  " + nested();
> }
>
> function notStrict() { return "I'm not strict."; }
>```


### Changes in Strict Mode

 Strict mode changes both syntax and runtime behavior. 
 
 Changes generally fall into these categories:  
  changes converting mistakes into errors (as syntax errors or at runtime),  
  changes simplifying how the particular variable for a given use of a name is computed,  
  changes simplifying eval and arguments,  
  changes making it easier to write "secure" JavaScript,  
  and changes anticipating future ECMAScript evolution.
  

#### Converting Mistakes into Errors

 Strict mode changes some previously-accepted mistakes into errors.  
 JavaScript was designed to be easy for novice developers, and sometimes it gives operations which should be errors non-error semantics.  
 Sometimes this fixes the immediate problem, but sometimes this creates worse problems in the future.  
 Strict mode treats these mistakes as errors so that they're discovered and promptly fixed. 
 
 First, strict mode makes it impossible to accidentally create global variables.  
 In normal JavaScript mistyping a variable in an assignment creates a new property on the global object and continues to "work" (although future failure is possible: likely, in modern JavaScript).  
 Assignments which would accidentally create global variables instead throw in strict mode:
 
>```
> 'use strict';
>                       // Assuming a global variable mistypedVariable exists
> mistypeVariable = 17; // this line throws a ReferenceError due to the 
>                       // misspelling of variable
>```


 Second, strict mode makes assignments which would otherwise silently fail to throw an exception.
 
 For example, `NaN` is a non-writable global variable.  
 In normal code assigning to `NaN` does nothing; the developer receives no failure feedback.  
 In strict mode assigning to `NaN` throws an exception.  
 Any assignment that silently fails in normal code (assignment to a non-writable global or property, assignment to a getter-only property, assignment to a new property on a non-extensible object) will throw in strict mode:  
 
 
>```
> 'use strict';
> 
> // Assignment to a non-writable global
> var undefined = 5; // throws a TypeError
> var Infinity = 5; // throws a TypeError
> 
> // Assignment to a non-writable property
> var obj1 = {};
> Object.defineProperty(obj1, 'x', { value: 42, writable: false });
> obj1.x = 9; // throws a TypeError
>
> // Assignment to a getter-only property
> var obj2 = { get x() { return 17; } };
> obj2.x = 5; // throws a TypeError
>
> // Assignment to a new property on a non-extensible object
> var fixed = {};
> Object.preventExtensions(fixed);
> fixed.newProp = 'ohai'; // throws a TypeError
>```


 Third, strict mode makes attempts to delete undeletable properties throw (where before the attempt would simply have no effect):
 
>```
> 'use strict';
> delete Object.prototype; // throws a TypeError
>```


 Fourth, strict mode prior to Gecko 34 requires that all properties named in an object literal be unique.  
 Normal code may duplicate property names, with the last one determining the property's value.
 But since only the last one does anything, the duplication is simply a vector for bugs, if the code is modified to change the property value other than by changing the last instance.
 
 Duplicate property names are a syntax error in strict mode:
 
>```
> 'use strict';
> var o = { p: 1, p: 2 }; // !!! syntax error
>```


 Fifth, strict mode requires that function parameter names be unique.
 In normal code the last duplicated argument hides previous identically-named arguments.
 
 Those previous arguments remain available through `arguments[i]`, so they're not completely inaccessible.
 Still, this hiding makes little sense and is probably undesirable (it might hide a typo, for example), so in strict mode duplicate argument names are a syntax error:
 
>```
> function sum(a, a, c) { // !!! syntax error
>   'use strict';
>   return a + b + c; // wrong if this code ran
> }
>```


 Sixth, strict mode in ECMAScript 5 forbids octal syntax.
 
 Octal syntax isn't part of ECMAScript 5, but it's supported in all browsers by prefixing the octal number with a zero: `0644 === 420` and `"\045" === "%"`.
 
 In ECMAScript 2015 Octal number is supported by prefixing a number with `"0o"`. i.e. 
 
>```
> var a = 0o10; // ES2015: Octal
>```
 
 
 Novice developers sometimes believe a leading zero prefix has no semantic meaning, so they use it as an alignment device — but this changes the number's meaning!
 The leading zero syntax for octals is rarely useful and can be mistakenly used, so strict mode makes it a syntax error:
 
>```
> 'use strict';
> var sum = 015 + // !!! syntax error
>           197 +
>           142;
> 
> var sumWithOctal = 0o10 + 8;
> console.log(sumWithOctal); // 16
>```
 
 
 Seventh, strict mode in ECMAScript 2015 forbids setting properties on primitive values.
 Without strict mode, setting properties is simply ignored (no-op), with strict mode, however, a `TypeError` is thrown.
 
>```
> (function() {
> 'use strict';
> 
> false.true = '';         // TypeError
> (14).sailing = 'home';     // TypeError
> 'with'.you = 'far away'; // TypeError
> 
> })();
>```


#### Simplifying variable uses

 Strict mode simplifies how variable names map to particular variable definitions in the code. 
 Many compiler optimizations rely on the ability to say that variable _X_ is stored in _that_ location: this is critical to fully optimizing JavaScript code.
 
 JavaScript sometimes makes this basic mapping of name to variable definition in the code impossible to perform until runtime.
 Strict mode removes most cases where this happens, so the compiler can better optimize strict mode code.
 
 
  First, strict mode prohibits with. The problem with with is that any name inside the block might map either to a property of the object passed to it, or to a variable in surrounding (or even global) scope, at runtime: it's impossible to know which beforehand.
  
  Strict mode makes with a syntax error, so there's no chance for a name in a with to refer to an unknown location at runtime:
  
>```
> 'use strict';
> var x = 17;
> with (obj) { // !!! syntax error
>   // If this weren't strict mode, would this be var x, or
>   // would it instead be obj.x?  It's impossible in general
>   // to say without running the code, so the name can't be
>   // optimized.
>   x;
> }
>```

 The simple alternative of assigning the object to a short name variable, then accessing the corresponding property on that variable, stands ready to replace `with`.
 
 Second, `eval` of strict mode code does not introduce new variables into the surrounding scope.
 In normal code `eval("var x;")` introduces a variable x into the surrounding function or the global scope.
 This means that, in general, in a function containing a call to `eval` every name not referring to an argument or local variable must be mapped to a particular definition at runtime (because that `eval` might have introduced a new variable that would hide the outer variable).
 
 In strict mode `eval` creates variables only for the code being evaluated, so `eval` can't affect whether a name refers to an outer variable or some local variable:
 
>```
> var x = 17;
> var evalX = eval("'use strict'; var x = 42; x;");
> console.assert(x === 17);
> console.assert(evalX === 42);
>```

 Relatedly, if the function `eval` is invoked by an expression of the form `eval(...)` in strict mode code, the code will be evaluated as strict mode code.
 
 The code may explicitly invoke strict mode, but it's unnecessary to do so.
 
>```
> function strict1(str) {
>   'use strict';
>   return eval(str); // str will be treated as strict mode code
> }
>
> function strict2(f, str) {
>   'use strict';
>   return f(str); // not eval(...): str is strict if and only
>                  // if it invokes strict mode
> }
>
> function nonstrict(str) {
>   return eval(str); // str is strict if and only 
>                     // if it invokes strict mode
> }
>
> strict1("'Strict mode code!'");
> strict1("'use strict'; 'Strict mode code!'");
> strict2(eval, "'Non-strict code.'");
> strict2(eval, "'use strict'; 'Strict mode code!'");
> nonstrict("'Non-strict code.'");
> nonstrict("'use strict'; 'Strict mode code!'");
>```


 Thus names in strict mode `eval` code behave identically to names in strict mode code not being evaluated as the result of `eval`.
 
 
 Third, strict mode forbids deleting plain names. `delete name` in strict mode is a syntax error:


>```
> 'use strict';
> 
> var x;
> delete x; // !!! syntax error
> 
> eval('var y; delete y;'); // !!! syntax error
>```


#### Making `eval` and `arguments` simpler

 Strict mode makes `arguments` and `eval` less bizarrely magical.
 
 Both involve a considerable amount of magical behavior in normal code: `eval` to add or remove bindings and to change binding values, and `arguments` by its indexed properties aliasing named arguments.

 Strict mode makes great strides toward treating `eval` and `arguments` as keywords, although full fixes will not come until a future edition of ECMAScript.
 
 
 First, the names `eval` and `arguments` can't be bound or assigned in language syntax.
 All these attempts to do so are syntax errors:
 
 
>```
> 'use strict';
> eval = 17;
> arguments++;
> ++eval;
> var obj = { set p(arguments) { } };
> var eval;
> try { } catch (arguments) { }
> function x(eval) { }
> function arguments() { }
> var y = function eval() { };
> var f = new Function('arguments', "'use strict'; return 17;");
>```

 Second, strict mode code doesn't alias properties of `arguments` objects created within it. 

 In normal code within a function whose first argument is `arg`, setting `arg` also sets `arguments[0]`, and vice versa (unless no arguments were provided or `arguments[0]` is deleted). `arguments` objects for strict mode functions store the original arguments when the function was invoked.
 `arguments[i]` does not track the value of the corresponding named argument, nor does a named argument track the value in the corresponding `arguments[i]`.

>```
> function f(a) {
>   'use strict';
>   a = 42;
>   return [a, arguments[0]];
> }
> var pair = f(17);
> console.assert(pair[0] === 42);
> console.assert(pair[1] === 17);
>```

 Third, `arguments.callee` is no longer supported. 
 In normal code `arguments.callee` refers to the enclosing function.
 
 This use case is weak: simply name the enclosing function! Moreover, `arguments.callee` substantially hinders optimizations like inlining functions, because it must be made possible to provide a reference to the un-inlined function if `arguments.callee` is accessed. 
 `arguments.callee` for strict mode functions is a non-deletable property which throws when set or retrieved:
 
>```
> 'use strict';
> var f = function() { return arguments.callee; };
> f(); // throws a TypeError
>```


#### "Securing" JavaScript


 Strict mode makes it easier to write "secure" JavaScript.
 Some websites now provide ways for users to write JavaScript which will be run by the website on _behalf of other users_.
 
 JavaScript in browsers can access the user's private information, so such JavaScript must be partially transformed before it is run, to censor access to forbidden functionality.
 JavaScript's flexibility makes it effectively impossible to do this without many runtime checks.
 
 Certain language functions are so pervasive that performing runtime checks has considerable performance cost. 
 A few strict mode tweaks, plus requiring that user-submitted JavaScript be strict mode code and that it be invoked in a certain manner, substantially reduce the need for those runtime checks.


 First, the value passed as `this` to a function in strict mode is not forced into being an object (a.k.a. "boxed").
 
 For a normal function, `this` is always an object: either the provided object if called with an object-valued `this`;
 the value, boxed, if called with a Boolean, string, or number `this`;
 or the global object if called with an `undefined` or `null` `this`.
 (Use `call`, `apply`, or `bind` to specify a particular `this`.)

 Not only is automatic boxing a performance cost, but exposing the global object in browsers is a security hazard, because the global object provides access to functionality that "secure" JavaScript environments must restrict.
 
 Thus for a strict mode function, the specified `this` is not boxed into an object, and if unspecified, `this` will be `undefined`:
 
>```
> 'use strict';
> function fun() { return this; }
> console.assert(fun() === undefined);
> console.assert(fun.call(2) === 2);
> console.assert(fun.apply(null) === null);
> console.assert(fun.call(undefined) === undefined);
> console.assert(fun.bind(true)() === true);
>```

 That means, among other things, that in browsers it's no longer possible to reference the window object through `this` inside a strict mode function.
 
 
 Second, in strict mode it's no longer possible to "walk" the JavaScript stack via commonly-implemented extensions to ECMAScript.
 
 In normal code with these extensions, when a function `fun` is in the middle of being called, `fun.caller` is the function that most recently called `fun`, and `fun.arguments` is the `arguments` for that invocation of `fun`.
 
 Both extensions are problematic for "secure" JavaScript, because they allow "secured" code to access "privileged" functions and their (potentially unsecured) arguments. If `fun` is in strict mode, both `fun.caller` and `fun.arguments` are non-deletable properties which throw when set or retrieved:
 
>```
> function restricted() {
>   'use strict';
>   restricted.caller;    // throws a TypeError
>   restricted.arguments; // throws a TypeError
> }
> function privilegedInvoker() {
>   return restricted();
> }
> privilegedInvoker();
>```


 Third, `arguments` for strict mode functions no longer provide access to the corresponding function call's variables. 
 
 In some old ECMAScript implementations `arguments.caller` was an object whose properties aliased variables in that function.
 
 This is a security hazard because it breaks the ability to hide privileged values via function abstraction; it also precludes most optimizations.
 
 For these reasons no recent browsers implement it. Yet because of its historical functionality, `arguments.caller` for a strict mode function is also a non-deletable property which throws when set or retrieved:
 
>```
> 'use strict';
> function fun(a, b) {
>   'use strict';
>   var v = 12;
>   return arguments.caller; // throws a TypeError
> }
> fun(1, 2); // doesn't expose v (or a or b)
>```


#### Paving the way for future ECMAScript versions


 Future ECMAScript versions will likely introduce new syntax, and strict mode in ECMAScript 5 applies some restrictions to ease the transition.
 It will be easier to make some changes if the foundations of those changes are prohibited in strict mode.
 
 
 First, in strict mode a short list of identifiers become reserved keywords. These words are `implements`, `interface`, `let`, `package`, `private`, `protected`, `public`, `static`, and `yield`.
 
 In strict mode, then, you can't name or use variables or arguments with these names.
 
>```
> function package(protected) { // !!!
>   'use strict';
>   var implements; // !!!
> 
>   interface: // !!!
>   while (true) {
>     break interface; // !!!
>   }
> 
>   function private() { } // !!!
> }
> function fun(static) { 'use strict'; } // !!!
>```


 Two Mozilla-specific caveats: 
 
 First, if your code is JavaScript 1.7 or greater (for example in chrome code or when using the right `<script type="">`) and is strict mode code, `let` and `yield` have the functionality they've had since those keywords were first introduced. 
 
 But strict mode code on the web, loaded with `<script src="">` or `<script>...</script>`, won't be able to use `let/yield` as identifiers. Second, while ES5 unconditionally reserves the words `class`, `enum`, `export`, `extends`, `import`, and `super`, before Firefox 5 Mozilla reserved them only in strict mode.
 
 
 Second, strict mode prohibits function statements not at the top level of a script or function. 
 In normal code in browsers, function statements are permitted "everywhere".
 
 _This is not part of ES5 (or even ES3)!_ It's an extension with incompatible semantics in different browsers.
 
 Future ECMAScript editions will hopefully specify new semantics for function statements not at the top level of a script or function.
 
 Prohibiting such function statements in strict mode "clears the deck" for specification in a future ECMAScript release:
 
>```
> 'use strict';
> if (true) {
>   function f() { } // !!! syntax error
>   f();
> }
> 
> for (var i = 0; i < 5; i++) {
>   function f2() { } // !!! syntax error
>   f2();
> }
> 
> function baz() { // kosher
>   function eit() { } // also kosher
> }
>```

This prohibition isn't strict mode proper, because such function statements are an extension of basic ES5. 
But it is the recommendation of the ECMAScript committee, and browsers will implement it.


### Strict Mode in Browsers

The major browsers now implement strict mode. 
However, don't blindly depend on it since there still are numerous Browser versions used in the wild that only have partial support for strict mode or do not support it at all (e.g. Internet Explorer below version 10!). 

_Strict mode changes semantics_. Relying on those changes will cause mistakes and errors in browsers which don't implement strict mode. 
Exercise caution in using strict mode, and back up reliance on strict mode with feature tests that check whether relevant parts of strict mode are implemented. 

Finally, make sure to _test your code in browsers that do and don't support strict mode_. 
If you test only in browsers that don't support strict mode, you're very likely to have problems in browsers that do, and vice versa.

