# ES6 Features

## What is ES6?  

ECMAScript 6 (ES6, often referred to as “Harmony”), is the upcoming sixth major release of the ECMAScript language specification. ECMAScript is the “proper” name for the language commonly referred to as JavaScript.  -Credit:  http://dev.venntro.com/2013/09/es6-part-1/

- ECMAScript 6 (ES6) is also known as ECMAScript 2015. Here's the specification:  http://www.ecma-international.org/ecma-262/6.0/

- Support for ES6 varies from browser to browser.  You can use the ES6 compatibility table to get an idea of the features supported by the browser you’re using right now:  http://kangax.github.io/es5-compat-table/es6/

- You can enable a Chrome browser to use ES6 via :
  - chrome://flags/
  - scroll down the page
  - enable **Experimental JavaScript**.

## Transpilers

Since ES6 is not compatible with today's browsers, you need a way to change code written in ES6 syntax to more vanilla JS.  This is a job for a _transpiler_.

A source-to-source compiler, transcompiler or transpiler is a type of compiler that takes the source code of a program written in one programming language as its input and produces the equivalent source code in another programming language or another version of the same language, like JS.  

**Babel** is a JavaScript compiler/transpiler.  Babel transforms your JavaScript. Babel has support for the latest version of JavaScript through syntax transformers. These plugins allow you to use new syntax, right now without waiting for browser support.

Babel even has a cool [try it out](http://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=let%20myFunction%20%3D%20x%20%3D%3E%20x*2) feature.  



## Constants

Support for constants (also known as "immutable variables"), i.e., variables which cannot be re-assigned new content.

CodePen:  http://codepen.io/tripott/pen/rjjMXK

```
// DEMO 1 - A variable cant be assigned new content.
const PI = 3.141593
console.log(PI > 3.0)
```

> Notice: this only makes the variable itself immutable, not its assigned content (for instance, in case the content is an object, this means the object itself can still be altered).  See below.

```
// DEMO 2 - but if a const is assigned an object, the content of the object can be changed.
const myObj = {firstName: "Steve", lastName: "Martin"}

console.log(myObj)  // => Object {
                            firstName: "Steve",
                            lastName: "Martin"
                          }

myObj.firstName = "Steven"

console.log(myObj)  // => Object {
                            firstName: "Steven",
                            lastName: "Martin"
                          }
```

> Best Practice: It's best to limit the mutability of a variable. When declaring variables, use `const`.  Only change to `let` or `var` when absolutely necessary.  

- Constants must have an initializer, unlike `let` or `var` declarations.

  ```
  var x; // x === undefined
  const z; // SyntaxError: const declarations must have an initializer

  const y = 10; // y === 10

  y = 20; // SyntaxError: Assignment to constant variable
  ```

## let

- The `let` statement declares a block scope local variable, optionally initializing it to a value.  `let` allows you to declare variables that are limited in scope to the block, statement, or expression on which it is used. This is unlike the `var` keyword, which defines a variable globally, or locally to an entire function regardless of block scope.

  https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let

  ```
  function varTest() {
    var x = 1;
    if (true) {
      var x = 2;  // same variable!
      console.log(x);  // 2
    }
    console.log(x);  // 2
  }

  function letTest() {
    let x = 1;
    if (true) {
      let x = 2;  // different variable
      console.log(x);  // 2
    }
    console.log(x);  // 1
  }
  ```

- Variables declared with a let statement are created as bindings on the lexical environment. A change to the specification of block statements in ES6 means that each block has its own lexical environment. In the above example, a new lexical environment is created when the block (the body of the if statement) is evaluated.

- Attempting to reference an identifier created as part of a let declaration before the declaration itself has been evaluated will result in an error:

  ```
  console.log(x); // ReferenceError: x is not defined
  let x = 10;   
  ```

- When using a `var` statement as a loop initializer the declaration will be hoisted as discussed above and the variable will be accessible throughout the execution context in which it appears. This can be a common cause of confusion for beginners, especially those coming from a language that does implement block scoping. With the addition of the let declaration we can ensure our loop counter is only accessible within its block:

  ```
  for (let i = 0; i < 10; i++) {
      console.log(i); // Prints 0 to 9
  }
  console.log(i); // ReferenceError: i is not defined
  ```
  Credit:  http://dev.venntro.com/2013/09/es6-part-2/


## Arrow functions

- An [arrow function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) expression has a shorter syntax than a function expression.

  ```
  // Before ...
  function (arguments) { expression }

  // After ...
  arguments => expression.

  ```
- Parens are optional depending on the number of arguments.

  ```
  //////////////////
  // Sample 1 - squaring a number
  //////////////////

  // Before...
  var square = function (x) {
    return x * x
  }

  // After...
  let square = x => x * x

  //////////////////
  // Sample 2 - Adding two numbers
  //////////////////

  // Before...
  var add = function (a, b) {
    return a + b;
  }

  // After...
  let add = (a, b) => a + b
  ```

- If using an expression after an arrow, the return is implicit, so no `return` is required. `return` is implied if using an expression after an arrow.

  ```
  //////////////////
  // Sample 1 - squaring a number
  //////////////////

  // Before...


  // After...


  ```

### Arrow functions are always anonymous

- The following examples anonymous functions are created:

  ```
  var f = function(x) {
   return x + 2
  }

  var myObject = {
    firstName: "William",
    lastName: "Defoe",
    fullName: function() {
      return this.firstName + " " + this.lastName
    }
  };

  myObject.fullName()  // returns "William Defoe"
  ```

  CodePen: http://codepen.io/tripott/pen/vggPPj



### EXERCISE:  Convert to arrow functions

Convert the functions in the following CodePen:  XXXXXXXX, to arrow functions.






## destructuring
