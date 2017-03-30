# High-Order Functions

Function that operate on other functions, either by taking them as arguments or returning them.

High-order functions allow us to abstract over actions, not just values.

- Functions that create new functions
- Functions that change other functions
- Functions that provide new types of control flow

## Taking Functions as Arguments

When you pass a function by name without parentheses, you are passing the function object itself. When you pass it with parentheses, you are passing the result of executing that function.

## Returning Functions as Results

JavaScript allows functions to return other functions as a result. This makes perfect sense, since functions are simply objects, they can be returned the same as any other value.

Defining a function as the return value of another function allows you to create functions that can be used as templates to create new functions. That opens the door to another world of functional JavaScript magic.

Higher-order functions are so basic to the way JavaScript works, you’re already using them. Every time you pass an anonymous function or a callback, you’re actually taking the value that the passed function returns, and using that as an argument for another function.

The ability of functions to return other functions extends the convenience of JavaScript, allowing us to create custom named functions to perform specialized tasks with shared template code. Each of these little functions can inherit any improvements made in the original code down the road, which helps us avoid code duplication, and keeps our source clean and readable.