# What is GetMyWeater API?
The GetMyWeather API provides a weather forecast for a given region and time. It provides the temperature, wind speed, humidity, and chance of precipitation.

# How can I use GetMyWeather API?

Developers who are familiar with HTML and Javascript can use GetMyWeather API for a variety of reasons:
* Provide weather information on websites and mobile applications.

* Add parameters to a code base so content is displayed as a function of the weather. This can be useful for sites that make recommendations or predications based on weather.

# How reliable are the results from GetMyWeather?

GetMyWeather's confidence is a function of how far in the future the request is made. Its confidence is high (up to 90 and 100 percent) for 1 and 2 days from the time the request is made. Its confidence decreases as predictions move further out. At 10 days out, GetMyWeather will be only 50 percent confident. After 10 days, the confidence range is significantly less than 50 percent.

# How are region and time determined?

A region is determined by providing two values: an origin and a radius. The origin must be given in latitude and longitude. The radius must be given as a numerical value (can it be floating point?) and represents meters from the origin.

The time is determined by providing a specific day at a specific time. The day must be provided within month/day/year format and the time must be provided in the hour/minute format using the 24 hour standard.

For example, if you wanted a forecast for Leicester, England within 100 meters of the city on a given day, you would supply the latitude and longitude for Leicester as the origin point, 100 as the value in meters away from the origin, and then the day, month, year, and then the hour and minute.

If you supplied 52.6369, 1.1398 and 100 and 09/07/2018/23/55, you would get a weather forecast within 100 meters of that lat/long on September, 7, 2018 at 11 PM and 23 minutes.

The forecast would encompass the following area within the red circle at 11:23 PM on September 7, 2018.

![radius map][/images/leicester-map-with-radius.jpg]


# What type and kind of data does GetMyWeather return?

GetMyWeather provides four weather values: temperature, humidity, wind speed, and chance of precipitation.

## Values

Value | Returned number | Example
----------| ---------- | ---
Temperature |  A number that represents degrees Fahrenheit | `72` means 72 degrees Fahrenheit
Wind speed | A number that represents kph (kilometers per hour) | `21` means 21 kph
Humidity | A number between 0-100 that represents a percentage| `80` means 80 percent humidity.
Precipitation | A number between 0-100 that represents a percentage| `50` means 50 percent chance of precipitation

# How much does GetMyWeather cost to use?

- First 100,000 calls/day:  $.01 cent per call
- After 100,000 calls/day contact us at 1-888-alan-getweather

# How do I make requests to GetMyWeather?

## To make a request, you will need to supply four parameters.

You will need to supply the following parameters:
 * **ORIGIN**: this must be supplied in latitude and longitude
 * **METERS AWAY FROM ORIGIN**: this must be supplied as a numerical value
 * **TIME**: this must be supplied in the month/day/year format and the time in hour/minute format
 * **API KEY**: this must be supplied for all requests


### Origin point in latitude and longitude

Provide latitude and longitude in the following format:

`<NN.NNNN>:<NN.NNNN>`

For example, Leicester's latitude and longitude would be supplied as the following:

`52.6369:1.1398`

**BE CAUTIOUS**: GetMyWeather must have location data in latitude:longitude format. If you provide incorrect values, you will get the following error message returned:
`error: invalid location data supplied`

#### What if I only have the zip code or address? Can I use that?

GetMyWeather only uses latitude and longitude. Therefore, you will need to convert a user's location value into latitude and longitude before making a request to the API.

Here is a reference link for converting location data: [How do I convert a location into latitude and longitude?](https://support.google.com/maps/answer/18539?co=GENIE.Platform%3DDesktop&hl=en)

### Meters away from origin

Provide a numerical value that represents the meters away from the origin.
(What is the largest value I can supply?)

**BE CAUTIOUS**: A value not within (range?) will return the following error message:

`error: radius value not within range`

### Time

Provide a time period in two-digit month, two-digit day, four-digit year, two-digit hour (24hr standard), and two-digit minute, with each value separated by a backslash.

mm/dd/year/hr/minute


For example, `09/07/2018/23/55` is a request on for September, 7, 2018 at 11PM and 23 minutes.

**BE CAUTIOUS**: Values not provided in this format will return the following error message:

`error: date range incorrect`

## Date provided and confidence of forecast

Predicting weather is hard. Use this table to accurately inform your users of the confidence for the forecast.

Days out | Confidence as a percentage
---- | ----
1 - 2 | 100 %
3 - 4 | 80 %
5 - 6 | 70 %
7 - 8 | 60 %
9 - 10 | 50 %
10 or more | less than 50 %


### API key
Register for a API key at getmyweather.com. To register, you will need a credit card.

**BE CAUTIOUS**: Without an API key, you cannot make a request. You will receive the following error message:
`error: request invalid`

# GetMyWeather request example

```javascript
//Injecting result into HTML page
<div id='forecast'></div>

//Initializing getWeather
<script type='text/javascript'>
var weatherForecast;
function init(){
weatherForecast =
  new getWeather (document.getElementByID('forecast'))
}
</script>

//Calling getWeather
<script async defer
src="https:www.getmyweather.com/getWeather?"
key=<Your_API_Key>&
callback=initMap&
location=<Lat:Long>&
specificity=<Specificity>&
time=<Time>&
>
</script>

```

#### Returned values

sample return package
```javascript

<div class="forcast">
    <div class="temperature">78</div>
    <div class="windspeed">15</div>
    <div class="chanceRain">30</div>
    <div class="humidity">80</div>
</div>
```

# What if I cannot get my API request to work?

Email alan.support@getmyweather.com or ask a question on our support forum at getmyweathersupport.com.

