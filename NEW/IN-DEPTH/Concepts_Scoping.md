# Scoping

There are 2 main scopes in JavaScript - Global and Local 

## Global scope
Variable that declared ouside of a function will belongs to the global scope which can be access anywhere in the code.

## Local scope
Each function has its own scope which will make any variable declaration inside of it can only access within that function and any nested funtions.

## Block-level scope - New local scope from ECMAScript 2015

From ECMAScript 6 (2015) JavaScript will now available for block scope
by using `let` keyword instead of `var` which can be used defined variables limiting their scope to the block in which they are declared

Unlike `var`, variables beclared using `let` aren't hoisted.