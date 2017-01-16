[Home](/)  

# Objects

Let's create a weather log of hourly weather readings.

- Date Ex: YYYY-MM-DD  such as 2017-01-26
- Time Ex: hh:mm:ss such as 15:58:59Z is equal to 10:58:59 AM EST
- Temperature (F)
- Heat Index

- Dew point (F)
- Humidity (%)
- Barometric Pressure (in)
- Visibility
- Windspeed
- Wind
  - direction (degrees):  Ex:  West, Calm, WNW, East, NNW, SSW
  - speed (mph) Ex: 4.6 mph, 8.1 mph
  - Gust speed (mph) 20 mph
- Precipitation (in) Ex: 0.12, 0.35, 0.00
  - Events


## Exercise Ideas

1. Using the browser's console, create a simple hourly weather observation for 10 AM EST for January 26, 2017 and set it to a variable named `weather`.:

  ```
  var weather = {
    date: "2017-01-26",
    time: "15:00:01Z",
    temp: 55,
    precip: 0,
    windSpeed: 5,
    windDirection: "WSW"
  }
  ```

2.  `push` the `weather` object into an array named `weatherObservations`

  ```
  var weatherObservations = []
  weatherObservations.push(weather)
  ```

3. Retrieve the first item in the array to display the weatherObservation:

  ```
  weatherObservations[0]
  ```

4. Using the first `weather` object as a guide.  Add the following weather observations into the array using the console.

  - date 2017-01-26, time 16:00:00Z, temp 57, precip .1, windSpeed 7, windDirection S
  - date 2017-01-26, time 17:00:03Z, temp 60, precip 0, windSpeed 3, windDirection SSW
  - date 2017-01-26, time 19:00:02Z, temp 62, precip .1, windSpeed 7, windDirection S


5. Using the console, display the 2nd temperature in the array.
6. Using the console, display the 3rd wind speed in the array.
7. Create a function named `getWeatherValue`, that accepts two parameters:
  - an array `index`, such as 0 for the first item, 1 for the second item, etc.
  - a weather `property` name as a string, such as "windSpeed" or "date".  


  Using the `index` and `property` parameters, return the value from the `weatherObservation` array.

  Here's an example of calling the function to return the time from the 2nd item in the array. 

  ```
  getWeatherValue(1, "time")  // returns "16:00:00Z"
  ```




[Home](/)  
