# Date Object
This object let us to work with dates (years, monthsm days, hours, minutes, seconds, and milliseconds)

Dates written as numbers, specifies the number of milliseconds since January 1, 1970, 00:00:00.


## Using Date object
Date objects are created with the new Date() constructor.

var variableName = new Date(Parameter);
- new Date(milliseconds)
- new Date(dateString)
- new Date(year, month, day, hours, minutes, seconds, milliseconds)


``
var currentDate = new Date();
```

## Here are some basic Date object's methods

### get group

getDate()
getDay()
getMonth()
getFullyYear()
getHours()
getMilliseconds()
getMinutes()

### to group
Convert time and day to strong.

toString()
toJSON()

### set group
setDate()


### formating group

## Methods that were deprecated, outdated, Not recommended to used anymore.
### year()

## Basic implementation of Date Object

### Create a function to return name of days.

```
function dayName(daynum, lang) {  
    if (!daynum){  
        console.log("Missing day number in dayName() function");  
    }  
    else if (isNaN(daynum)) {  
        console.log("Wrong day input in dayName() function, it should be   number and between 0-6");  
    }  
    else if (daynum > 6) {  
        console.log("Wrong day number in dayName() function, the number   should be between 0-6");  
    }  
    else {  
        var day = parseInt(daynum);  
        switch(day){  
            case 0: result = "Sunday"; break;  
            case 1: result = "Monday"; break;  
            case 2: result = "Tuesday"; break;  
            case 3: result = "Wednesday"; break;  
            case 4: result = "Thursday"; break;  
            case 5: result = "Friday"; break;  
            case 6: result = "Saturday"; break;  
        }  
        return result;  
    }  

}  

\\ Test function \\ it should return Sunday in console  
console.log(dayName(0))  
```
