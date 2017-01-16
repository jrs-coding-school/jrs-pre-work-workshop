# Arrays

> JavaScript provides a data type specifically for storing sequences of values.  It is called an _array_ and is written as a list of values between square brackets, separated by commas.

```
var listOfNumbers = [2, 3, 5, 7, 11];
```

- Numbers, Booleans, and strings are the bricks that data structures are built from. But you can’t make much of a house out of a single brick. Objects allow us to group values—including other objects—together and thus build more complex structures.
- JavaScript provides a data type specifically for storing sequences of values. It is called an _array_ and is written as a list of values between square brackets, separated by commas.

```
var imANewButEmptyArray = []
var listOfNumbers = [2, 3, 5, 7, 11];
```

- The notation for getting at the elements inside an array also uses square brackets. This will look up the element that corresponds to the index given by the expression in the brackets.
- The first index of an array is zero, not one. So the first element can be read with listOfNumbers[0].  This is called "zero-based counting".

```
var listOfNumbers = [2, 3, 5, 7, 11];
console.log(listOfNumbers[0]);     // returns 2
console.log(listOfNumbers[1]);     // returns 3
console.log(listOfNumbers[1 - 1])  // returns 2
console.log(listOfNumbers[3])      // returns 7
console.log(listOfNumbers[5])      // returns undefined
```

### Array Properties and Methods

- Almost all JavaScript values have properties.
- To get the length of a string we could use the `.length` property of a `string` or `array`:

```
var myString = "Cat"
myString.length             // returns 3

var listOfNumbers = [2, 3, 5, 7, 11]
listOfNumbers.length        // returns 5
```

### Accessing properties in JavaScript

Almost all JavaScript values have properties. The exceptions are `null` and `undefined`.

> If you try to access a property on one of these nonvalues, you get an error.

two most common ways to access properties in JavaScript:

- dot notation:  Ex:  myVar.length
- square bracket notation:  Ex: myObject[x]

### dot notation

Here are some examples of dot notation when accessing a property:

When using a dot, the part after the dot _must be a valid variable name_, and it directly names the property.

In the example below `myString.length`  fetches the property of value named `length`.

```
var myString = "Cat"
myString.length
// returns 3.  
//"length" property is a valid variable name, since length exists for all string objects.
```

### square brackets

When using square brackets, the expression between the brackets is _evaluated_ to get the property name.

value[x] tries to evaluate the expression x and uses the result as the property name.

```
var propertyName = "length"
var lastName = "Ottinger"
lastName.length         // -> returns a value of 8
lastName[propertyName]  // -> returns a value of 8
```

### Array Methods

- The `push` method can be used to add values to the end of an array.
- The `pop` method does the opposite: it removes the value at the end of the array and returns it.
- The `join` method flattens all the array values into a string.

Demo:  Use the console to play with an array.  Push, pop, length and index and join.  For example:  

```
// Here's an empty array named "theSentence"
var theSentence = []

// Let's add a word to the array
theSentence.push("The")
console.log(theSentence)
theSentence.push("cow", "jumped", "over", "the", "moon.")

//An array of strings can be flattened to a single string with the join method.
theSentence.push("The", "dog", "chased", "the", "cat.")
theSentence.join(" ")
```

> DEMO:  Fill an array with the fizz and the buzz.


[Home](/)
