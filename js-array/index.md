# Arrays

> JavaScript provides a data type specifically for storing sequences of values.  It is called an _array_ and is written as a list of values between square brackets, separated by commas.

```
var listOfNumbers = [2, 3, 5, 7, 11];
```

- Numbers, Booleans, and strings form the basis of larger, more complex data structures.  

## Arrays can contain objects

Arrays can contain objects. What is an object?

- "An object is an unordered set of name/value pairs. An object begins with `{` (left brace) and ends with `}` (right brace). Each name is followed by `:` (colon) and the name/value pairs are separated by `,` (comma).  -credit:  http://www.json.org/

- Here is an object in JavaScript named `author`.  It is formed using JSON.  JSON (JavaScript Object Notation) is a lightweight data-interchange format.

- A value can be a string in double quotes, or a number, or true or false or null.

  ```
  var author = {
    firstName: "William",
    lastName: "Buckley",
    birthDate: "1925-11-27",
    gender: "Male",
    deceased: true
  }
  ```

- A value within an object can be another object, such as `wind`.

  ```
  var weather = {
  date: "2017-01-26T15:00:01Z",
  temp: 55,
  precip: .11,
  wind: {
    windSpeed: 5,
    windDirection: "WNW",
    gusts: 20
  }
  ```

- Values can be nested. A value within an object can be an array.

  ```
  var player = {
    name: "Michael Jordan",
    mvpSeasons: ["1987-88","1990-91","1991-92","1995-96","1997-98"],
  }
  ```

- A value within an object can be an array which contains objects.

CodePen YouTube JSON Data Example:  http://codepen.io/tripott/pen/dNOZpV


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

### Array Methods `push`, `pop`, `join`

- The `push` method can be used to add values to the _end_ of an array.
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
### Array Methods `unshift` and `shift`

- The method for _adding_ to the start of an array is `unshift`.

```
// Here's an empty array named "theSentence"
var theSentence = []
theSentence.push("the", "dish", "ran", "away", "with", "the", "spoon.")
theSentence.unshift("The", "cow", "jumped", "over", "the", "moon", "and")
theSentence.join(" ")  // => "The cow jumped over the moon and the dish ran away with the spoon."
```

- The method for _removing_ from the start of an array is `shift`

```
theSentence.shift()  // => "The"
theSentence.shift()  // => "cow"
theSentence.shift()  // => "jumped"
theSentence.join(" ") // => "over the moon and the dish ran away with the spoon."
```

## Higher ordered functions - Using an array's built in `filter()` method

![Filter the dogs](/assets/img/filter-dogs.png)

CodePen:  http://codepen.io/tripott/pen/bggPrm

```
const animals = [
  {name: "Anna", species: "Cat"},
  {name: "Jack", species: "Cat"},
  {name: "Dash", species: "Dog"},
  {name: "Tootles", species: "Cat"},
  {name: "Mr. Handsome", species: "Cat"},
  {name: "Tucker", species: "Dog"}
]

var isDog = function (animal) {
  return animal.species ==="Dog"
}

var dogs = animals.filter(isDog)

console.log(dogs)

/* A new filtered array of dogs is returned.
[
  {name: "Dash", species: "Dog"},
  {name: "Tucker", species: "Dog"}
]
*/
```

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter

- The `filter()` method creates a new array with all elements that pass the test implemented by the provided function.  The original array is not mutated.

- `filter()` calls a provided _callback function_ once for each element in an array, and constructs a new array of all the values for which callback returns a value that coerces to `true`.

- The callback function you provide should be a _predicate_ function to test each element of the array. Return `true` to keep the element.

- The data (array) is called a _functor_.  The `filter` method loops over the data (functor) and applies the supplied callback function/predicate function for each item in functor.



  ```
  function isBigEnough(value) {
    return value >= 10   
  }

  var filtered = [12, 5, 8, 130, 44].filter(isBigEnough)
  // filtered is [12, 130, 44]


  // We can rewrite the code by placing the function as an anonymous function inside the filter:

  var filtered = [12, 5, 8, 130, 44].filter(function (value) {
    return value >= 10   
  })

  // filtered is [12, 130, 44]

  ```

### Summary

  `filter()` will loop through each value in the array. For each value in the array, `filter()` will pass the value into the callback function. It expects the callback function to return either `true` or `false` to tell whether the value should be in the new, returned array.  The callback is a predicate functions which is a function that takes one item as input and returns either true or false based on whether the item satisfies some condition.After filter is done looping through the array, it will return a new filtered array.  The data (array) is called a _functor_.

### EXERCISE: Higher order functions and filter

Let's watch the following video as a group.  It helps to explain:

  - Passing functions as values
  - Higher order functions
  - `filter()`

  https://www.youtube.com/watch?v=BMUiFMZr7vk

### EXERCISE: Filtering Arrays

- Fork the CodePen below.
- Use JavaScript's built in `filter()` method to filter the array of weather observations.  Only observations that have a wind gusts over 60 should be returned.

  Fork this CodePen:  http://codepen.io/tripott/pen/XppLwj

  Use this CodePen if you need an example to guide you along: http://codepen.io/tripott/pen/bggPrm

## DEMO: Higher order functions - Using Ramda's `filter`

- While JavaScript provides some methods to manipulate arrays, like filter and map. Functional JavaScript libraries like RamdaJS provide us with a rich series of functions/methods to manipulate objects and arrays.

> Ramda is awesome. Learn it. Love it. Use it whenever you can.

- Just like JavaScript's built-in `filter` function, Ramda's `filter` function takes a _predicate_ and a "filterable" thing like an object or array.

- Remember, a _predicate_ is a function that takes one item as input and returns either `true` or `false` based on whether the item satisfies some condition.

RamdaJS: http://ramdajs.com/docs/#filter
CodePen:  http://codepen.io/tripott/pen/ZLLgjy

## DEMO: Higher order functions - Using Ramda `reject`

```
const animals = [
  {name: "Anna", species: "Cat"},
  {name: "Jack", species: "Cat"},
  {name: "Dash", species: "Dog"},
  {name: "Tootles", species: "Cat"},
  {name: "Mr. Handsome", species: "Cat"},
  {name: "Tucker", species: "Dog"}
]

var isDog = function (animal) {
  return animal.species ==="Dog"
}

var notDogs = R.reject(isDog, animals)

/*
[
  {"name":"Anna","species":"Cat"},
  {"name":"Jack","species":"Cat"},
  {"name":"Tootles","species":"Cat"},
  {"name":"Mr. Handsome","species":"Cat"}
]
*/

```

RamdaJS: http://ramdajs.com/docs/#reject
CodePen: http://codepen.io/tripott/pen/gggVpZ

## EXERCISE:  Ramda `filter` and `reject`

- Fork the following CodePen: http://codepen.io/tripott/pen/XppLwj
- Rename the CodePen: **Workshop 101 - JS - Exercise: Ramda Filter and Reject**
- Add the following RamdaJS code library into the CodePen via the JS settings (cog):

  `https://cdnjs.cloudflare.com/ajax/libs/ramda/0.23.0/ramda.min.js`

- Once the RamdaJS code library has been added it will be accessible via the `R` object:

  `R.filter`

- Use Ramda's `filter` function to return weatherObservations with precipitation.
- Use Ramda's `reject` function to return weatherObservations with no precipitation.


## Higher order functions - Using Ramda `map`

After a while, writing a for loop becomes background noise.  Wouldn't you rather focus on solving the problem than writing a loop for the 100th time?

Ramda has a `map` function that takes two things.  A function and data.  The data is called a _functor_.  The map function loops over the data (functor) and applies (maps) the supplied function for each item in functor.

CodePen: http://codepen.io/tripott/pen/pRezra

```
var weatherObservations = [{
  date: "2016-09-29T12:00:01Z",
  temp: 80,
  precip: 0.25,
  wind: {
    windSpeed: 33,
    windDirection: "N",
    gusts: 40
  }
}, {
  date: "2016-09-29T13:00:01Z",
  temp: 82,
  precip: 0.25,
  wind: {
    windSpeed: 49,
    windDirection: "N",
    gusts: 60
  }
}, {
  date: "2016-09-29T14:00:01Z",
  temp: 84,
  precip: 0.25,
  wind: {
    windSpeed: 70,
    windDirection: "N",
    gusts: 80
  }
}, {
  date: "2016-09-29T15:00:01Z",
  temp: 84,
  precip: 0.25,
  wind: {
    windSpeed: 66,
    windDirection: "N",
    gusts: 70
  }
}, {
  date: "2016-09-29T16:00:01Z",
  temp: 85,
  precip: 0.25,
  wind: {
    windSpeed: 90,
    windDirection: "N",
    gusts: 100
  }
}, {
  date: "2016-09-29T17:00:01Z",
  temp: 86,
  precip: 0.25,
  wind: {
    windSpeed: 78,
    windDirection: "N",
    gusts: 80
  }
}, {
  date: "2016-09-29T18:00:01Z",
  temp: 88,
  precip: 0.11,
  wind: {
    windSpeed: 73,
    windDirection: "WNW",
    gusts: 80
  }

}, {
  date: "2017-01-26T16:00:01Z",
  temp: 57,
  precip: 0,
  wind: {
    windSpeed: 7,
    windDirection: "NNW",
    gusts: 70
  }
}, {
  date: "2017-01-26T17:00:01Z",
  temp: 58,
  precip: 0.25,
  wind: {
    windSpeed: 6,
    windDirection: "N",
    gusts: 15
  }
}]

var convertToC = function(observation) {
  return {
    date: observation.date,
    tempF: observation.temp,
    tempC: Math.round(((observation.temp - 32) / 1.8)  * 100) / 100
  }
}

console.log(R.map(convertToC, weatherObservations))

```

We can use Ramda's interactive documentation to try out the `map` function!

http://ramdajs.com/docs/#map

## EXERCISE: Higher order functions - Using Ramda `map`

- Fork the following CodePen: http://codepen.io/tripott/pen/pRezra
- Create a function and apply the function to each of the functor's values.
- The function should convert each wind speed from miles per hour (mph) to:  
  - knots (0.8689762 *  Wind mph)
  - meters per second (0.44704 * Wind mph)
  - kilometers per hour (1.609344 * Wind mph)
- Return an array containing objects.  Each object in the array should have the following shape:

  ```
  {
    date: "2016-09-29T16:00:01Z",
    wind: {
      windSpeedMPH: 90,
      windSpeedKTS: 78.20,
      windSpeedMPS: 40.23,
      windSpeedKMH: 144.84,
    }
  }
  ```


[Home](/)
