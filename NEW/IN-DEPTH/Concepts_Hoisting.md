# Hoisting

It is a behavior of JavaScript that moving any declaration to the top
of the current scope (scripts or functions)

A variable can be declared after it has been used, 
so to say that we can use any variable before declared it.

_this term you'll not find in JavaScript document_

"It's a general way of thinking about how execution context (specifically the creation and execution phases) work in JavaScript"

### Only declarations are hoists, and not innitializations
If you initialize variable by some value, it won't be hoisted.
so your variable will returns undefined.


## Why it is so important to know!? 
"Hoisting is (to many developers) an unknown or overlooked behavior of JavaScript.  
If a developer doesn't understand hoisting, programs may contain bugs (errors).  
To avoid bugs, always declare all variables at the beginning of every scope.  
Since this is how JavaScript interprets the code, it is always a good rule."  *[1]*

# References

*[1]* [JavaScript Hoisting | W3School ](https://www.w3schools.com/js/js_hoisting.asp)
