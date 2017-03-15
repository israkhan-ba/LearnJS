# Loop
The way to work repeatly with condition to define how many round the loop should work.


## for()

for( condition #1, condition #2, condition #3) {
      // something to do each loop
}
- condition #1: The initial condition of loop iteration
- condition #2: The condition for continue loop working
- condition #3: The condition after each loop finish

```
for(i=0, i<10, i++ {
    console.log("i : " + i);
}
```

## while()


var conditionalVariable = VALUE;
while(CONDITION) {
        // something to do
        // ConditionalVariable (Don't forget to change)
}

```
var i=0;
while(i<10){
    console.log("i : " + i);
    i++;
}
```

## do {} while ()
similar to 'while' but it will do once before check condition

do {
    // something to do first.
} while(CONDITION)

```
var i=0;
do {
    console.log("i : " + i);
    i++;
}   while (i<10);
```

## foreach()
