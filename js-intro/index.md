[Home](/)  |  [JS Intro](/js-intro)  |  [Arrays](/js-array)  |  [Objects](/js-objects)  |  [Functions](/js-functions) |  [ES6](/js-ES6)

# Introduction to JavaScript

> Software is eating industries. JavaScript is eating software.

JavaScript is a programming language commonly used in web development. It was originally developed by Netscape as a means to add dynamic and interactive elements to websites.  Alongside HTML and CSS, JavaScript is one of the three core technologies of World Wide Web content production; the majority of websites employ it, and all modern Web browsers support it without the need for plug-ins.

JavaScript is also used in environments that are not Web-based.  JavaScript runs everywhere from a web browser to a web server to a database to a drone to a [refrigerator](https://github.com/GEMakers/gea-plugin-refrigerator).  

In this session we will explore some JavaScript fundamentals including:

- **Values** - Every value has a type that determines its role.
- **Operators** - Combine and transform values with operators.
- **Expressions** - A fragment of code that produces a value.
- **Variables** - A variable is used within a computer program to remember something.
- **Environment** - A program starts up in its environment which _is not empty_. It contains variables to interact with the surrounding system.  
- **Functions**
- **Control Flow** - Control different routes for the code to flow based on a Boolean (true/false) value.
- **Arrays** - JavaScript provides a data type specifically for storing sequences of values.

>  [MDN JavaScript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)

## Values

Every value has a type that determines its role. There are six basic types of values in JavaScript:

- number
- strings
- Booleans (True or False)
- objects
- functions
- undefined values

### numbers

The `Number` JavaScript object allows you to work with numerical values.

> [MDN JavaScript Reference- Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

#### Type Conversion

`Number` can be used to perform a type conversion.  You can convert strings to numbers.

```
Number("123")     // 123
Number("12.3")    // 12.3
Number("")        // 0
```

If the argument cannot be converted into a number, it returns `NaN`.

```
Number("foo")     // NaN
```

#### `Number.isNaN()`

Use `Number.isNaN()` to determine whether the passed value is `NaN`.  If the given value is NaN, `true` will be be returned.

CodePen: http://codepen.io/tripott/pen/LxWgGM

```
// Is the value passed equal to NaN?
console.log(Number.isNaN(15))       // false
console.log(Number.isNaN("Doggy"))  // false
console.log(Number.isNaN(result))   // false
console.log(Number.isNaN(NaN))      // true
```

### strings

A `String` object represents strings and support for manipulating them. A `String` object comes with built-in properties.  

> [MDN JavaScript Reference- Strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

#### `toUpperCase`

- Every string has a `toUpperCase` property, which is a method/function.
- Properties that contain functions are generally called methods of the value they belong to. As in, “toUpperCase is a method of a string”.

```
var myString = "Cat"
myString.toUpperCase()  //returns CAT
```

##### EXERCISE:  `toLowerCase()`

- Create a CodePen to transform a string to lower case.  Output the transformed string to the console using console.log().

#### `length`

- A String has a `length` property which reflects the length of the string.

```
var myString = "Cat"
myString.length      //returns 3
```

#### `split()`

- The `split()` method splits a String object into an array of strings by separating the string into substrings.

CodePen: http://codepen.io/tripott/pen/wgJEBN

```
var braveNewWorldQuote = "There's always soma to calm your anger, to reconcile you to your enemies, to make you patient and long-suffering. In the past you could only accomplish these things by making a great effort and after years of hard moral training. Now, you swallow two or three half-gramme tablets, and there you are. Anybody can be virtuous now. You can carry at least half your morality about in a bottle."

var quoteArray = braveNewWorldQuote.split(" ")

console.log(quoteArray)
/*
["There's", "always", "soma", "to", "calm", "your", "anger,", "to", "reconcile", "you", "to", "your", "enemies,", "to", "make", "you", "patient", "and", "long-suffering.", "In", "the", "past", "you", "could", "only", "accomplish", "these", "things", "by", "making", "a", "great", "effort", "and", "after", "years", "of", "hard", "moral", "training.", "Now,", "you", "swallow", "two", "or", "three", "half-gramme", "tablets,", "and", "there", "you", "are.", "Anybody", "can", "be", "virtuous", "now.", "You", "can", "carry", "at", "least", "half", "your", "morality", "about", "in", "a", "bottle."]
*/

console.log(quoteArray[2])   // "soma"

const months = "Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec"

const monthsArray = months.split(",")
console.log(monthsArray)      
/*
["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"]
*/
console.log(monthsArray[4])   // "May"
```

##### EXERCISE: `split()`

- Fork the CodePen: http://codepen.io/tripott/pen/wgJEBN
- Split the `braveNewWorldQuote` using the `and` separator.
- Display the results to the console using console.log.

#### `substring()`

The `substring()` method returns a subset of a string between one index and another, or through the end of the string.  The method takes a start and optional end index.

CodePen: http://codepen.io/tripott/pen/bgqxjG

```
// The `substring()` method returns a subset of a string between one index and another,
//  or through the end of the string.  The method takes a start and optional end index.

var title = "A Brave New World"

console.log(title.substring(2))      // "Brave New World"
console.log(title.substring(8))      // "New World"
console.log(title.substring(8,11))   // "New"
console.log(title.substring(2,7))    // "Brave"
console.log(title.substring(7,2))    // "Brave"
```

## Operators

Combine and transform values with operators:

- Arithmetic + - * % /
- String concatenation (+)  
- Comparison (==, !=, ===, !==, <, >, <=, >=)
- Logic (&&, ||)
- Unary (- to negate a number, ! to negate logically, and typeof to find a value’s type)
- Ternary (?:) to pick one of two values based on a third value.

### DEMO Add Operator

- CodePen: http://codepen.io/tripott/pen/RKaqPv
- Create a function named `add()`.  The function should accept two parameters named `add1` and `add2`.  The function should add the numbers and display the result using `alert()`.
- Test the function in the console window.
- Use an `onClick()` event handler to call the `add()` function from the pulse button.

### Events

The Web platform provides several ways to get notified of events on a web page.  The platform provides a set of specific _on-event_ handlers.  The on-event handlers are a group of properties offered by HTML elements , such as links, buttons, images, forms, etc. to help manage how that element reacts to events like being clicked, detecting pressed keys, getting focus, etc.

For example, in the previous demo, we specified an **onClick** event handler for the `<a>` element.

### DEMO Multiply Operator

Create a function named `mult()` .  The function should accept two parameters, multiply and display the result.

### Student Exercises

- Instructor "slacks" the url to the **JRS Pre-workshop: JS demos** pen
- Students fork the pen  http://codepen.io/tripott/pen/dNRpbN?editors=1111.  
- Create the `add()` and `mult()` functions by copying instructors code from screen.
- Create corresponding "pulse" buttons to call your `add()` and `mult()` functions.
- Create `minus()` and `divide()` functions and corresponding "pulse" buttons.

### Comparison Operators

Logical operators are typically used with Boolean (logical) (true/false) values.  

> > [MDN JavaScript Reference- Strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators)

#### Logical AND (`&&`)

When used with Boolean values, && returns true if both operands are true; otherwise, returns false.

#### Logical OR (`||`)

When used with Boolean values, || returns true if either operand is true.

#### Short-circuit evaluation



### Equality

JavaScript has both strict and type–converting comparisons. A strict comparison (e.g., ===) is only true if the operands are of the same type and the contents match. The more commonly-used abstract comparison (e.g. ==) converts the operands to the same type before making the comparison.  - [MDN Comparison Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)

> You can get into trouble with `==`.  It's safer to use `===` to perform a strict comparison which compares the type and content.  

#### Equality (==) versus strict equality (===)

CodePen: http://codepen.io/tripott/pen/XpMxvG

If the operands are of different types, `==` and `!=` will attempt to convert them to the same type before making the comparison.  When comparing a number and a string, the string is converted to a number value.   If one of the operands is Boolean, the Boolean operand is converted to 1 if it is true and +0 if it is false.

```
console.log("Ex.1 Equality", 1 == 1)              // "Ex.1 Equality" true
console.log("Ex.2 Equality", 1 == '1')            // "Ex.2 Equality" true
console.log("Ex.3 Equality", 1 == true)           // "Ex.3 Equality" true
console.log("Ex.4 Equality", 0 == false)          // "Ex.4 Equality" true
```

The strict equality operators (=== and !==) are intended for performing equality comparisons on operands of the same type. If the operands are of different types, the result is always false so 5 !== '5'.

```
console.log("Ex.5 Strict Equality", 1 === 1)      // "Ex.5 Strict Equality" true
console.log("Ex.6 Strict Equality", 1 === '1')    // "Ex.6 Strict Equality" false
console.log("Ex.7 Equality", 1 === true)          // "Ex.7 Equality" false
console.log("Ex.8 Equality", 0 === false)         // "Ex.8 Equality" false
console.log("Ex.9 Equality", true === true)       // "Ex.9 Equality" true
```

### Logic operators




## Program Structure

> "...A program is built out of statements, which themselves sometimes contain more statements. Statements tend to contain expressions, which themselves can be built out of smaller expressions.
Putting statements after one another gives you a program that is executed from top to bottom. You can introduce disturbances in the flow of control by using conditional (if, else, and switch) and looping (while, do, and for) statements..”

### Expressions

A fragment of code that produces a value is called an _expression_. Combine expressions to express arbitrarily complex computations.  An expression corresponds to a sentence fragment.

```
(2 > 5) // evaluates to false
(5 > 2) // evaluates to true
```

### Statements

- A _statement_ corresponds to a full sentence in a human language. A program is simply a list of statements.  The simplest kind of statement is an expression with a semicolon after it.
- A statement could change a value on the computer screen.
- A statement could change the internal state of the machine in a way that will affect the statements that come after it. These changes are called _side effects_.

### Variables

- Variables are used within a computer program to remember things.  It’s how a program keep its internal state.  

- Use variables to catch and hold values.

```
var caught = 5 * 5;
```

- The keyword `var` indicates we want to define a variable. It is followed by the name of the variable and, if we want to immediately give it a value, by an `=` operator and an expression:

```
var favColor = "blue"
var favColor = prompt("What is your favorite color?", "blue")
```

After a variable has been defined, its name can be used as an expression:

```
var ten = 10;
console.log(ten * ten);
```

- A variable _points_ at a value.  It is **NOT** tied to that value forever.
- The `=` operator can be used at any time on existing variables to disconnect them from their current value and have them point to a new one.

Try the following in the console within your web browser or codepen.

```
var favColor = "blue"
console.log(favColor)
favColor = "yellow"
console.log(favColor)
```

- When you define a variable without giving it a value, there's nothing to grasp, so it ends in thin air.

- If you ask for the value of an empty variable, you’ll get the value "undefined".  

```
var favColor2
console.log(favColor2)
favColor2 = favColor
console.log(favColor2)
```

### Environment

- When a program starts up, this environment _is not empty_. It always contains variables.  
- Some of these variables provide ways to interact with the surrounding system.  
- JavaScript can run in lots of different environments from a web browser, a server, a drone, or even a refrigerator.  
- When JavaScript is running inside of a web browser, there are variables and functions to inspect and influence the currently loaded website and to read mouse and keyboard input.
- `Math` is a built-in JavaScript object that has properties and methods for mathematical constants and functions.
- The `alert()` method displays an alert dialog with the optional specified content and an OK button.
- The `console.log()` function writes out its arguments to some text output device.
- The `prompt()` function can be used to ask an “open” question. The first argument is the question, the second one is the text that the user starts with. A line of text can be typed into the dialog window, and the function will return this text as a string.

```
prompt("Tell me everything you know.", "...");
```

- `confirm()` asks the user an **OK** or **Cancel** question. This returns a Boolean value of `true` if the user clicks **OK** and `false` if the user clicks **Cancel**.

> Let's play around with some of these functions in the console.

```
Math.min(100, 2, -1, 6, 8)
Math.max(1, 0, -1, 2, -45)
alert("Hello World")
console.log(10 * 10)
prompt("What is your dream?","To become a rapper.")
```

### Calling a function

- A function is a piece of a program that you can “call”, “invoke”, “run”, and “execute”, or “apply”.
- You can call a function by putting parentheses after an expression that produces a function value.

- Functions may also produce values.  When a function produces a value, it is said to _return_ that value.

> Let's play around with some of these functions in the console.

- Values given to functions are called _arguments_.  The `alert()` function needs only one of them, but other functions might need a different number or different types of arguments.

```
alert("Hello World")
Math.min(2, 4)
isNaN(9)
!isNaN(9)
isNaN("cat")
!isNaN("cat")
confirm("Shall we dance?")
```

- function calls can be used within larger expressions:

```
console.log(Math.min(2, 4) + 100)
```

- The `Number()` function happens to return `NaN` when you give it a string that doesn’t represent a valid number.
- `confirm()` asks the user an **OK** or **Cancel** question. This returns a Boolean value of `true` if the user clicks **OK** and `false` if the user clicks **Cancel**.
- The `isNaN()` or "is Not a Number" function is a standard JavaScript function that returns `true` only if the argument it is given is `NaN`.

> Let's play around with some of these Functions in the console, first.  Then, we can write a function and wire the function up to a new pulse button.


### STUDENT EXERCISE

- Create a pulse button that calls a function named `times2()`.  Within this function   `prompt()` for a number and double it.  Store the result within a variable.
- Send result to the console via `console.log()`.


## CONTROL FLOW

- Statements are executed, predictably, from top to bottom.
- Executing statements in straight-line order isn’t the only option we have. An alternative is conditional execution, where we choose between two different routes based on a Boolean (true/false) value.

### `if`

- Conditional execution is written with the `if` keyword.
- We just want some code to be executed if, and only if, a certain condition holds true. - The keyword `if` executes or skips a statement depending on the value of a Boolean expression (true/false).
- The deciding expression is written after the keyword, between parentheses, followed by the statement to execute:

```
var age = 3

if (x>2) {
  console.log("x is " + age + " which is greater than 2")
}
```

### `else`

You will often have to write code that handles the alternate path. The `else` keyword can be used, together with `if`, to create two separate, alternative execution paths.

```
var age = 1

if (x > 2) {
    console.log("x is " + age + " which is greater than 2")
} else {
    console.log("x is not greater than 2")
}
```

### `else if`

If we have more than two paths to choose from, multiple if/else pairs can be “chained” together:

```
var age = 1

if (x < 1) {
    console.log("x is less than 1")
} else if (x === 1) {
    console.log("x is 1")
} else if (x === 2) {
    console.log("x is 2")
} else {
    console.log("x is " + x)
}
```

### DEMO - COMPARE

For this demo I will create a `fatcat()` function that prompts for a cat's weight.  We will store the weight to a variable. We will use `if` and `else if` and `else` to compare and `console.log()` to make a comment about the cat's weight.

- The `prompt()` function can be used to ask an “open” question. The first argument is the question, the second one is the text that the user starts with. A line of text can be typed into the dialog window, and the function will return this text as a string.

### DEMO - SQUARE

For this demo, we will use functions that exist within the browser environment:
- We will ask for a number with `prompt()`
- Try and convert it to a number with `Number()`
- Perform a check to ensure it's a number with `!isNaN`
- `confirm()` that the user wishes to square the number (9 x 9 = 81 or 2 x 2 = 4).
- `alert()` the user of the outcome.
- Cover all alternate paths.  
  - Prompted value is not a number
  - User decides not to square the number.


### for loops

- All the statements that are related to the “state” of the loop are grouped together.

```
for (var number = 0; number <= 12; number = number + 2)
 ...
```

- The parentheses after a "for" keyword must contain two semicolons.
- The part before the first semicolon initializes the loop, usually by defining a variable.  A “counter” variable is created to track the progress of the loop:

```
var number = 0
```

- The second part is the expression that checks whether the loop must continue.  A test expression usually checks whether the counter has reached some boundary, yet:
```
number <= 12
```

- The final part updates the state of the loop after every iteration:

```
number = number + 2
```

### DEMO - EVEN NUMBERS

I'll create a function that prompts for a number and print out all even numbers, up to the prompted number.

```
function evenNumbers() {
  var topNumber = prompt("Enter a number", 12)

  for (var number = 0; number <= topNumber; number = number + 2) {
    console.log(number);
  }
}
```

### DEMO - Compute the power of a number

Create a function that computes the power of a number.  Prompt for a base and exponent.

## STUDENT EXERCISE - Looping a triangle

- Write a program to output the following triangle:

```
#
##
###
####
#####
######
#######
```


## STUDENT EXERCISE - Fizz Buzz Part 1 of 2

- Write a program that uses `console.log()` to print all the numbers from 1 to 100, with two exceptions:
- For numbers divisible by 3, print "Fizz" instead of the number
- For numbers divisible by 5 (and not 3), print "Buzz", instead.

** TIPS **

- Going over a series of numbers is clearly a looping job
- Selecting what to print is a matter of conditional execution
- there are three possible outcomes for every number: Fizz, Buzz or the number
- Using the remainder or modulo (`%`) operator for checking whether a number is divisible by another number (has a remainder of zero)

```
console.log(6 % 3)        // returns a remainder of 0
console.log(10 % 3)       // returns a remainder of 1
console.log(33 % 5)       // returns a remainder of 3
console.log(6 % 3 === 0)  // returns true.  6 is divisible by 3.
console.log(10 % 3 === 0)  // returns false.  10 is not divisible by 3.
```

## STUDENT EXERCISE - Fizz Buzz Part 2 of 2

- Modify your program to print "FizzBuzz", for numbers that are divisible by both 3 and 5
- Continue to print "Fizz" or "Buzz" for numbers divisible by only one of those

[Home](/)  
