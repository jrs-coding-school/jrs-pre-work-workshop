# Functions

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

- Variables that are declared outside of functions are dangerous.  Global variables are accessible from within a function.  Danger!

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

```
var myGun = function () {
  var ammo = ["pew", "pew", "pew"]
  console.log(ammo.join(" "))
}

var fireGun = function(mode) {
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
fireGun()       // => clickclickclick
```
