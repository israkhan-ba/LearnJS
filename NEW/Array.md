Array

Array is an object, have methods and properties of it's own,
and can store any type of data in to it, ordering by index number starting with 0.


Creating array
- var arrayName = [] //  
- var arrayName = new Array(); // Not recommended

Checking array
- length // Property to count how many value in the array
// arrayName.length;

Adding array
- push() // Method to add data to the last order of the array
// array.push();

Clear array 
- arrayName.length = 0; // Make an array length to be 0, all data will be destroyed. - The recommended way.

- arrayName = []; // Not recommended

Display array
- arrayName[#] // varName = Array name; # = Show value from the order number of the array 
// arrayName[0];

Deleting value in an array
- pop() // Method to remove the last value of the array
// arrayName.pop();

- shift() // Method to remove the first value of the array
// arrayName.shift();

- splice() // Method to remove elements without leaving "holes" in the array
// arrayName.splice(#, ##); First parameter '#' is the index number define to start element removal, and the second '##' is the length to remove from the defined index.

Return data from an array
- toString() // Method to convert all value of an array by order as a long string, join each data with commas.
// arrayName.toSting();

- join() // Method to convert all values of an array by order as a long string, similar to toString() except join() can change data seperator by argument (Argument must be STRING)
// arrayName.join(" + "); Make "+" as string seperator instead of comma

