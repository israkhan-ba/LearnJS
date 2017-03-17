## Objects
Object group together a set of variables and functions to create a model of something

#### Object Properties
Property is a variable which is a part of an object, it tell us about the object such as name, the age of perso, number of page of a book, etc.

##### Ways to create an object (The basic way)
1. Directly assign to a variable
> `var person = {firstName: "John" lastName: "Smith", age: 30}`  
> 

2. Using *__new__* keyword
> `var person = new Object();`  
>
> **// Now adding properties and methods to the object.**  
> ```
> person.firstName = "John";
> person.lastName = "Smith";
> person.age = 30;
> ```

Both will create an object named *person* which has 3 properties
and when we test it to console.log, they will return the same
> console.log(person)
> Object {firstName: "John" lastName: "Smith", age: 30}

##### Access an object's property 
To access a property of an object we have several ways to do.  
1. We use **.** (Dot operator) and property name following after the object name to access it
> `console.log(person`**`.`**`firstName);`  

2. We use **["**...**"]** (Brackets) with double-quotes and property name within, following after the object name
> `console.log(person`**`["firstName"]`**`)`

> // this will display in console: John

#### Object Methods
Methods are actions that did something with the object, each method is a function which is a part of an object. It represent tasks that is associated with the object.

We may assume roughly that every in the JavaScript is an object.

To add an object a method, it's simple like adding a property without double-quotes  
and assign an anonymous function as it's value
> `var person = {`  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
> `firstName: "John";`  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
> `lastName: "Smith";`  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
> **`getFullName: function(){`**  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
> `return person.firstName + " " + person.lastName;`    
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
> `}`  
> `}`

So this is how we create a method
Then we trying it with console.log

> `console.log(`**`person.getFullName()`**`);`  
> // This will return **John Smith** in console.log

Don't forget that we need to use **() (Parenthesis)** after a method to call it, like we call a function.

#### Execution context