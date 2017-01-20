[Home](/)  |  [JS Intro](/js-intro)  |  [Arrays](/js-array)  |  [Objects](/js-objects)  |  [Functions](/js-functions) |  [ES6](/js-ES6)

# JavaScript Functions

## Ways to define a function

- Use a variable to define a function.  The variable value is the definition of the function.
- `function` is the keyword that starts the definition of the function.

```
// pass an array and returns the last item in the array or string.

var last = function (arr) {

  if (typeof arr != 'undefined') {
    return arr[arr.length - 1]
  } else {
    return undefined
  }

}

last([2,3,4,2,1,1,2,3])  // => 3
last("apples")           // => "s"
last(11)                 // => undefined
last()                   // => undefined
```

- You could write the same function like this:

```
function last (arr) {
  if (typeof arr != 'undefined') {
    return arr[arr.length - 1]
  } else {
    return undefined
  }
}
```

## Parameters

- functions can have an optional set of parameters and a required body which is wrapped in curly braces.  Here's a function with no parameters.

```
var boom = function () {
  alert("BOOM")
}
```

## Parameters and Scope

- function parameters are variables. Parameters are scoped to the function in which their defined.  But their values are provided by the caller of the function.

> parameters are local to the function.

```
var a = "apples"

function capitalize(word) {

    // slice() extracts the text from one string and returns a new string.
    return word.charAt(0).toUpperCase() + word.slice(1);
}

capitalize(a)     // returns "Apples"
console.log(a)    // returns "apples"
```

- like parameters, variables declared within the function are local to the function.  

> In JavaScript, functions are the only things that create a new scope.

```
var x = "outside";

var f1 = function() {
  var x = "inside f1";
};
// run the f1() function which sets a new "x" variable that is scoped local to the function.
f1();    
console.log(x);   // => outside
```

## Pure functions and side effects

- functions may optionally produce a value.  A "pure function" is a function that maps its input value(s) into an output value.

```
var add = function(a, b) {
  return a+b
}
```

- functions may optionally produce a side effect.  A "side effect" is any effect other than that return value.  The sample below does NOT produce a value but DOES produce a side effect of raising an alert dialog.  

```
var boom = function () {
  alert("BOOM")
}
```

- Variables that are declared outside of functions are dangerous.  Global variables are accessible from within all the functions.  Danger!  Side effects ahead!

```
var imOutside = "I hope I don't change! That would be a nasty side effect.";

var functionsHaveAccessToGlobalVariables = function() {
  imOutside = "whoops! side effect.";
};

console.log(imOutside); // => I hope I don't change! That would be a nasty side effect.
functionsHaveAccessToGlobalVariables();
console.log(imOutside);   // => whoops! side effect.
```



## Functions are values

A function value acts like other types of values.

- You can use it in an expression.
- It can be assigned a new value.

```
var fireGun = function(mode) {
  var myGun = function () {
    var ammo = ["pew", "pew", "pew"]
    console.log(ammo.join(" "))
  }

  if (mode==="boom") {
    myGun = function () {
      var ammo = ["boom", "boom", "boom"]
      console.log(ammo.join("!"))
    }
  } else if (mode==="safe") {
    myGun = function () {
      var ammo = ["click", "click", "click"]
      console.log(ammo.join(""))
    }
  }

  myGun()
}

fireGun()  // => "pew pew pew"
fireGun("boom") // => "boom!boom!boom"
fireGun("safe") // => clickclickclick
```

- Pass a function as an argument to another function.

  - CodePen 1: http://codepen.io/tripott/pen/VPPLmL
  - CodePen 2: http://codepen.io/tripott/pen/bggdYY


- functions can be returned as a value from a function!

```
function iReturnAFunction(n) {
  var localVariable = n;
  return function() { return localVariable; };
}

// set the variable `one` with a value of a function.
var one =  iReturnAFunction(1)
// call the `one` function via `one()`
one()   // returns 1

```

- Local variables (those declared with `var` inside of a function) are “re-created” every time a function is called.

CodePen:  http://codepen.io/tripott/pen/oBBbNd

```
function iReturnAFunction(n) {
  var localVariable = n;
  return function() { return localVariable; };
}

// set the variable `one` with a value of a function.
var one =  iReturnAFunction(1)
// call the `one` function via `one()`
one()   // returns 1

var two = iReturnAFunction(2)
two()
```

## Closure

- Declaring a local variables inside or "enclosed" within a function is called a _closure_.  

- The local variable is only accessible from within the function.  This closure helps to protect the value of the variable, freeing you from worrying about side effects.

- A parameter is itself a local variable.

CodePen: http://codepen.io/tripott/pen/MJJKrv

## Higher Order Functions

- functions are regular values, just like a number or a string.
- functions can be returned as a value from a function.  You can have functions that create and return new functions.  

CodePen:  http://codepen.io/tripott/pen/WRRrgo

- functions can be passed as a parameter value to a function.

CodePen: http://codepen.io/tripott/pen/KaaMVE

## EXERCISE:  Create a Higher Order Function 1

- Create a function named `lessThan` that accepts a number as a parameter.  
- The return value from `lessThan` should be a function that accepts a second number as a parameter.
- When the second function is called, check to see of the second parameter provided is less than the first parameter.  The second function should return a `true` if the second parameter is less than the first parameter value, otherwise, return `false`.  
- Save your work to a CodePen.  Slack the instructor when you are done.


## Optional Arguments

- JS is "open-minded" when it comes to parameters/arguments for a function.
- Pass too many arguments and they are ignored by the function.
- Pass too few and the missing parameters will be assigned a value of `undefined`.

> It's easy to mess things up!  You can not pass enough arguments and JS _will not complain_.  This can make your program hard to debug.  Precision is a virtue.

> The good news is that arguments can be "optional".  If a value for a argument is not provided by the caller you _could_ provide a default value.

```
function power(base, exponent) {
  if (exponent == undefined)
    exponent = 2;
  var result = 1;
  for (var count = 0; count < exponent; count++)
    result *= base;
  return result;
}

console.log(power(4));
// → 16
console.log(power(4, 3));
// → 64
```
