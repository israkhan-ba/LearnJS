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