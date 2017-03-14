# Functions
Function is the way to repeat working with some condition to change result.

4 main kinds of function.
1. A function with no parameter, no output returns.
2. A function with no parameter, has some output returns.
3. A function with parameter, no output returns.
4. A function with parameter, has some output returns.

Some function may require a parameter to work, some might not.


//Creating a basic function

function functionName(PARAMETER) {
    // do something
}

    // Example.
    function testFunction(WriteSomething){
        console.log(WriteSomething);
    }


    //Calling the basic function
    functionName(PARAMETER);

    // Calling test
    testFunction();
    testFunction("Hello");
        // This will show "Hello" in console as an output.


// Create a function that are assigned to a variable
var variableName = function(PARAMETER){
    // do something
}

    // Example
    var testVarFunction = function(WriteSomething){
        console.log(WriteSomething);
    }

    // Calling variable function test
    testVarFunction();
    testVarFunction("This is a variable function");
    
This function will not hoisted as any value of variables will not being hoisted. And it will throw exception error if you call the function before declairation.