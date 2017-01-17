[Home](/)  

# Objects

- You can create an object using curly brace notation.  
- Inside the curly braces, include properties separated by commas.
- To create a property provide:
  - name
  - colon
  - value.
- Note the `events` property. An array is a value so we can place an array inside an object.

```
var weatherObservation = {
  dateTime: "2017-01-26T16:00:01Z",
  humidityPct: 80,
  forecast: "Fog early with sunny skies by mid morning.  Partly cloudy in the afternoon with an 80 percent chance of thunderstorms in the afternoon. Wind gusts up to 30 mph.",
  events: ["Fog", "Sun", "Partly Cloudy", "Thunderstorms", "Strong Wind Gusts"],
  "did it rain": true
}
```

- Read property values using dot notation to access property values.

```
var weatherObservation = {
  dateTime: "2017-01-26T16:00:01Z",
  humidityPct: 80,
  forecast: "Fog early with sunny skies by mid morning.  Partly cloudy in the afternoon with an 80 percent chance of thunderstorms in the afternoon. Wind gusts up to 30 mph.",
  events: ["Fog", "Sun", "Partly Cloudy", "Thunderstorms", "Strong Wind Gusts"],
  "did it rain": true
}

console.log(weatherObservation.humidityPct)   // => 80
```

- Reading a property that doesn’t exist produces an `undefined` value.

```
var weatherObservation = {
  dateTime: "2017-01-26T16:00:01Z",
  humidityPct: 80,
  forecast: "Fog early with sunny skies by mid morning.  Partly cloudy in the afternoon with an 80 percent chance of thunderstorms in the afternoon. Wind gusts up to 30 mph.",
  events: ["Fog", "Sun", "Partly Cloudy", "Thunderstorms", "Strong Wind Gusts"],
  "did it rain": true
}
console.log(weatherObservation.temp)          // => undefined

```

- Again, read property values using dot notation to access property values.  Both strings and arrays have a `length` property. The `events` property has 5 items within the array.

```
var weatherObservation = {
  dateTime: "2017-01-26T16:00:01Z",
  humidityPct: 80,
  forecast: "Fog early with sunny skies by mid morning.  Partly cloudy in the afternoon with an 80 percent chance of thunderstorms in the afternoon. Wind gusts up to 30 mph.",
  events: ["Fog", "Sun", "Partly Cloudy", "Thunderstorms", "Strong Wind Gusts"],
  "did it rain": true
}

console.log(weatherObservation.events.length) // => 5

```

- We can use the built in JSON object to 'stringify' an object. This creates a string out of the object.

```
var weatherObservation = {
  dateTime: "2017-01-26T16:00:01Z",
  humidityPct: 80,
  forecast: "Fog early with sunny skies by mid morning.  Partly cloudy in the afternoon with an 80 percent chance of thunderstorms in the afternoon. Wind gusts up to 30 mph.",
  events: ["Fog", "Sun", "Partly Cloudy", "Thunderstorms", "Strong Wind Gusts"],
  "did it rain": true
}

console.log(JSON.stringify(weatherObservation))  // =>

 {"dateTime":"2017-01-26T16:00:01Z","humidityPct":80,"forecast":"Fog early with sunny skies by mid morning.  Partly cloudy in the afternoon with an 80 percent chance of thunderstorms in the afternoon. Wind gusts up to 30 mph.","events":["Fog","Sun","Partly Cloudy","Thunderstorms","Strong Wind Gusts"]}
```

- Properties whose names are not valid variable names or valid numbers have to be quoted.

```
var profile = {
  firstName: "Steve",
  lastName: "Martin",
  "is wild and crazy": true
}
```
- Assign a value to a property expression with the `=` operator. This will replace or create a new property on the object.

```
var profile = {
  firstName: "Steve",
  lastName: "Martin",
  "is wild and crazy": true
}

profile.firstName = "Steven"
profile.entertainerType = "Comedian"

console.log(profile)  // => Object {firstName: "Steven", lastName: "Martin", is wild and crazy: true, entertainerType: "Comedian"}

JSON.stringify(profile)  // => "{"firstName":"Steven","lastName":"Martin","is wild and crazy":true,"entertainerType":"Comedian"}"
```

- A unary operation is an operation with only one operand.
- The `delete` operator is a unary operator that removes a property from an object.
- If the `delete` operator succeeds, it sets the property or element to `undefined`. The `delete` operator returns `true` if the operation is possible; it returns `false` if the operation is not possible.

```
var profile = {
  firstName: "Steve",
  lastName: "Martin",
  "is wild and crazy": true
}

delete profile.lastName             // => true
delete profile["is wild and crazy"] // => true

console.log(profile)  // => Object {firstName: "Steve"}
```

- The binary `in` operator returns a `Boolean` value that indicates whether that object has that property.

```
var profile = {
  firstName: "Steve",
  lastName: "Martin",
  "is wild and crazy": true
}

delete profile.lastName            
console.log(profile.lastName)         // => undefined
console.log("lastName" in profile);   // => false
```

- Objects can contain objects. The `wind` property value is an object that contains its own name value pairs: `windSpeed`, `windDirection`, and `gusts`.

```
var weatherObservation = {
  date: "2017-01-26T15:00:01Z",
  temp: 55,
  precip: .11,
  wind: {
    windSpeed: 5,
    windDirection: "WNW",
    gusts: 20
  }
}
```

- Object can contain arrays.  An array can contain objects.  The `events` property contains an array which contains three objects:

```
var weatherObservation = {
  date: "2017-01-26",
  humidityPct: 80,
  forecast: "Fog early with sunny skies by mid morning.  Partly cloudy in the afternoon with an 80 percent chance of thunderstorms in the afternoon. Wind gusts up to 30 mph.",
  events: [{
    name: "Fog",
    time: "08:00:01Z",
    temp: 55,
    dewpoint: 56
  }, {
    name: "Light Fog",
    time: "09:00:01Z",
    temp: 56,
    dewpoint: 58
  }, {
    name: "Clear",
    time: "13:00:01Z",
    temp: 65,
    dewpoint: 58
  }]
}

console.log(weatherObservation.events[2])   // => Object {
                                                    dewpoint: 58,
                                                    name: "Clear",
                                                    temp: 65,
                                                    time: "13:00:01Z"
                                                  }

console.log(weatherObservation.events[1].time) // => "09:00:01Z"
```


## DEMO: Using objects and arrays, let's create a weather log of hourly weather readings.

- Create an object containing the following weather observation data.  

  - date - 2017-01-26T15:00:01Z
  - temp - 55
  - precip - .11
  - wind
    - windSpeed- 5,
    - windDirection - WNW
    - gusts - 20

- Add the object to an array named `weatherObservations`.
- Add two more objects to the array.
- Display the first item from the array.
- Display the last item from the array.
- Display the `temp` object from an item in the array.
- Display the `wind` object from an item in the array.
- Display the `gusts` property from the `wind` object from an item in the array.

## Student Exercise

- Using codepen, create a simple hourly weather observation for 10 AM EST for January 26, 2017 and set it to a variable named `weather`.:

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

- `push` the `weather` object into an array named `weatherObservations`
- Using the console within codepen, retrieve the first item in the array to display the `weatherObservations` object:
- Using the first `weather` object as a guide.  Push additional weather observations into the array.
  - date 2017-01-26, time 16:00:00Z, temp 57, precip .1, windSpeed 7, windDirection S, gusts 20
  - date 2017-01-26, time 17:00:03Z, temp 60, precip 0, windSpeed 3, windDirection SSW, gusts 22
  - date 2017-01-26, time 19:00:02Z, temp 62, precip .1, windSpeed 7, windDirection S, gusts 25
- Display the `temp` property value from the 2nd item in the array.
- Display the `windSpeed` property value from the last item in the array.

## DEMO:  Return a value from an object in an array

- Create a function named `getWeatherValue`, that accepts two parameters:
  - an array `index` parameter, such as 0 for the first item, 1 for the second item, etc.
  - a weather `property` name parameter, such as "windSpeed" or "date".  

- Using the `index` and `property` parameters, return the property value from the `weatherObservation` array.  
- Call the function to return the time from the 2nd item in the array.

## EXERCISE: Return the wind object

- Fork the pen:  http://codepen.io/tripott/pen/oBzrBp
- Create a function named `getTheWind` that accepts a single parameter named `index`.
- Return the `wind` object for the index parameter value.

## DEMO: Ramda's lensIndex and view

- Ramda is a practical functional library for JavaScript programmers.  It never mutates user data.
- The Ramda library has been added to the pen: http://codepen.io/tripott/pen/GrjbEw.
- Ramda is available as the variable `R` on the browser's global scope (environment).
- Use Ramda's `lensIndex` function to return a lens for a given index
- Return the wind object for the first item item in the array.

## DEMO:  Looping through Arrays

Looping through an array is easy once you're comfortable with the `length` property of an array.

pen: http://codepen.io/tripott/pen/JERqoP

## DEMO: Finding an item

You can search for an item in an array by writing a function that loops through an array.  When the expression is true, return the first found item.

http://codepen.io/tripott/pen/RKGmpp

## EXERCISE: Find and return an item

- Using the previous code pen as a start, fork the pen (http://codepen.io/tripott/pen/RKGmpp).  
- Write a function called `findAWindSpeed` that loops through the array, searching for a specific windspeed.  Return the first _object_ you find with a windspeed equal to 5.

## DEMO: Filtering an array

- Using the previous code pen as a start, fork the pen (http://codepen.io/tripott/pen/wgowWP)
- Create a function named `precipitation` that _returns a new array_ that includes any weather observation objects where it either raining or not raining.
- The `precipitation` function should accept the following parameters:
  - `observations` - an array of weather observation objects
  - `isRaining` - boolean

## EXERCISE: Filtering an array - HURRICANE!

- Using the following code pen as a start, fork the pen (http://codepen.io/tripott/pen/VPmZzm)
- Create a function named `hurricane` that _returns a new array_ that includes any weather observation objects where wind gusts are greater are either:

  - Normal (<39 mph)
  - Tropical storm level (39–73 mph)
  - Hurricane level (=>74 pmh)

- The `hurricane` function should accept the following parameters:
  - `observations` - an array of weather observation objects
  - `windLevel` - string.  Valid value are either "Normal", "Tropical Storm", or "Hurricane".


## DEMO: Mapping

Values of the type `object` are arbitrary collections of properties, and we can add or remove these properties as we please.

We can transform an array by looping (mapping) through an array and creating a new array with containing new objects.  

- IMPORTANT! The original array is left untouched. We do not _mutate_ the original array.
- We simply loop/map over the original array to create new objects with a different shape.
- There are third party libraries that handle common mapping, filtering, finding, etc. operations on objects and arrays.  For now, we will do things the "old school" way.
- While the old school way works, it requires you writing more code, increases the risk of introducing bugs and mutating state (mutating the original array in this case).

- The following code create's new, empty object with no properties.

```
var newObj = {}
console.log(newObj)  // => Object {}
```
- Adding properties is easy!

```
var newObj = {}
newObj.firstName = "Steve"
newObj.lastName = "Martin"
console.log(newObj)    // =>  Object {
                                firstName: "Steve",
                                lastName: "Martin"
                                }
```

http://codepen.io/tripott/pen/PWGvPj

## EXERCISE: Mapping

- Loop over the array of `weatherObservations` data
- Transform each object into a new object and return a new array.
- Each new object in the returned array should have the following structure:
- We'll use the [momentjs](https://momentjs.com/docs/#/displaying/) library to help us format a date.  

```
[
{
  year: "2017",
  month: "01",
  day: "26",
  hours: "17",
  minutes: "00",
  seconds: "01",
  isRaining: true,
  windGusts: 22
}, ...
]
```


## DEMO: Ramda Mapping



## DEMO: Ramda Filtering
Ramda's `filter` function takes a _predicate_ and a "filterable" thing like an object or array.

A predicate is a function that takes one item as input and returns either true or false based on whether the item satisfies some condition.

## Find an object in an array

## Find item in array using a value deep in another object.

[Home](/)  
