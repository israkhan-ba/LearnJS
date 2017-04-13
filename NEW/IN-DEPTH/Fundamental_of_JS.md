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


### Expression

**Expression** intended to produces or evaluates some value without any side effect, the value may be a number, a string, or a logical value. Conceptually, there are two main type of expressions: those that assign a value to a variable, and those that simply have a value.


### Expression statement

If any expression that have produces side effect we will called them Expression statements.

Because **statements** can contain **expression** so wherever JavaScript expects a statement, we can also write an expression in to that but not a vice versa (we can't write a statement where JavaScript expects an expression)

### Code block
A block set that use to group statements , expression and declaration together (and can be zero statement either), functions, or if statement are some sort of block statements

In JavaScript, Blocks can be nested in any block.

### Values & Data Types
Everything in computer is just data (and yes only data) and each and every data has its own role.

Most of data are seperated to things called value, so values are some thing that represent some kind of data which will be stored in some way (like in memory).

And each value have a type, which determines the kind of role it can play.

In JavaScript there are basically 8 data types, which catagorized as 3 categories.  
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

## Composite Data Types

- **Object** (Data type) 
An object datatype, in computer science, is a value in memory which is possibly referenced by an identifier.
It is a data type which is collecion of properties and methods

 - **Objects** (itself)  
JavaScript Objects are collecion of properties and methods which will be contained inside curly brackets `{ }` in the format of `key : value` paring 

 - **Arrays**  
A container-like value which is an object data type, it's can contain values serially in an index manner which we call them elements, start counting each elements from index 0, and when there are changes in an array, it will resort the index number.  
You can contain any data type in an array, also nest it with an other arrays or objects.


### Variable

Variable is a container that used for storing data

In JavaScript, Variable are declared by using `var` key word (Also we can initialize variable with values but it's not necessary to use `var` key word)

