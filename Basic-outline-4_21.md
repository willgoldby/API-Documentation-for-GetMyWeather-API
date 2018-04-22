# What is GetMyWeater API?
The GetMyWeather API provides weather forecasts for a user-specified region and time. It provides the temperature, wind speed, humidity, and the chance of precipitation for a given region at a given that time.

# How can I use GetMyWeather API?

Developers can use the GetMyWeather API for a variety of reasons.
* Provide weather information websites and mobile applications.

* Add parameters to code. For example, certain content should be displayed when certain weather conditions exists, you can use GetMyWeather to check for those conditions. This can be useful for sites that make recommendations or predications based on weather.

# How reliable are the results from GetMyWeather?

GetMyWeather's confidence is a function of how far in the future the request is. Its confidence is high (up to 90 and 100 percent) for 1 and 2 days from the time the request is made. Its confidence decreases as predictions move further out. At 10 days out, GetMyWeather will be only 50 percent confident. After 10 days, the confidence range is significantly less than 50 percent.

# How are region and time determined?

A region is determined by two values: origin and radius. The origin must be given in latitude and longitude. The radius must be given as a numerical value (?can it be floating point) and represent meters from the origin.

The time is determined by a day and time. The day must be provided within month/day/year format and time must be provided in the hour/minute format using the 24 hour standard.

For example, if you wanted a forecast for Leicester, England within 100 meters of the city on a given day, you would supply the latitude and longitude for Leicester as the origin point, 100 as the value in meters away from the origin, and then the day, month, year, and then the hour and minute.

For example, if you supplied 52.6369, 1.1398 and 100 and 09/07/2018/23/55, you would get a weather forecast within 100 meters of that lat/long on September, 7, 2018 at 11 PM and 23 minutes.

The forecast would encompass the following area within the red circle at 11:23 PM on September 7, 2018.
![image of Leicester with radius](/images/leicester-map-with-radius.jpg)


# What type and kind of data does GetMyWeather return?

GetMyWeather provides four weather parameters: temperature, humidity, wind speed, and chance of precipitation.

## Parameters

Parameter | Returned value | Example
----------| ---------- | ---
Temperature |  A number that represents degrees Fahrenheit. | `72` means 72 degrees Fahrenheit
Wind speed | A number that represents kph (kilometers per hour) | `21` means 21 kph
Humidity | A number between 0-100 that represents a percentage| `80` means 80 percent humidity.
Precipitation | A number between 0-100 that represents a percentage| `50` means 50 percent chance of precipitation

# What do I need to use this API?

To use GetMyWeather, you will need know to simple HTML and Javascript syntax.

# How much does this it cost?

- First 100,000 calls/day:  $.01 cent per call
- After 100,000 calls/day contact us at 1-888-alan-getweather

# How do I make requests to GetMyWeather?

## To make a request, you will need to supply four values.

You will need to supply the following information:
 * An **origin** in latitude and longitude
 * A numerical value that represent **meters away from origin**
 * The **time** in month/day/year format and the time in hr/minute format
 * An **API key**.


#### Get My Weather request example

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
    <div class="trust">80</div>
</div>
```


### Origin point in latitude and longitude

Provide latitude and longitude in the following format:

`<NN.NNNN>:<NN.NNNN>`

For example, Leicester's latitude and longitude would be supplied as the following:

`52.6369:1.1398`

#### What if I only have the zip code or address? Can I use that?

GetMyWeather only uses latitude and longitude. Therefore, you will need to convert a user's location value into latitude and longitude before making a request to the API.

Here is a reference link for converting location data: [How do I convert a location into latitude and longitude?](https://support.google.com/maps/answer/18539?co=GENIE.Platform%3DDesktop&hl=en)

### Meters away from origin

Provide a numerical value that represents meters away from origin.
(?What is the largest value I can supply)

**BE CAUTIOUS**: A value not within ?range? will return the following error message:

`error: radius value not within range.`

### Time

Provide a time period in two-digit month, two-digit day, four-digit year, two-digit hour (24hr standard), and two-digit minute, with each value separated by a backslash.

mm/dd/year/hr/minute


For example, `09/07/2018/23/55` is a request on for September, 7, 2018 at 11PM and 23 minutes.

**BE CAUTIOUS**: Values not provided in this format will return the following error message:

`error: date range incorrect.`

#### Date provided and confidence of forecast

Predicting weather is hard. Use this table to accurately inform your users of the confidence for the forecast.

Days out | Confidence as a percentage
---- | ----
1 - 2 | 100 %
3 - 4 | 80 %
5 - 6 | 70 %
7 - 8 | 60 %
9 - 10 | 50 %
10 or more | less than 50 %



### API Key
** Do more than tell developers what they can expect within those ranges.
'If you do this, this will happen. If you put too small of a location, you will get x returned.' I need to tell developers of the CONSEQUENCES of their calls for all the parameters. **





some users will not have lat long, so convert zip to lat long ie campers, or areas that change
