/*
1. No parameter, no output returns.
2. No parameter, have some output returns.
3. Have parameter, no output returns.
4. Have parameter, have some output returns.

Some function may require a parameter to work, some might not.
*/

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


// Create a function as a variable
var variableFunction = function(PARAMETER){
    // do something
}

    // Example
    var testVarFunction = function(WriteSomething){
        console.log(WriteSomething);
    }

    // Calling variable function test
    testVarFunction();
    testVarFunction("This is a variable function");