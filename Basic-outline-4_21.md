# What is the GetMyWeater API?
The GetMyWeather API provides micro weather forecasts. It provides the temperature, wind speed, humidity, and numerical value for the chance of precipitation.

# How can I use the GetMyWeather API?

Developers can use the GetMyWeather API for a variety of reasons.
* Provide weather information for users of their websites or mobile applications.

* Add parameters to their code. For example, if temperature and wind speed are above or below certain values, the website content or application will display different information. This can be useful for sites the make recommendations or predications.

# How reliable are the results from GetMyWeather?

GetMyWeather's confidence in its predictions are a function of how are in the future GetMyWeather makes forecast. Its confidence is high (up to 90 and 100 percent) for 1 and 2 days from the present moment. The confidence decreases as predictions move further out from the moment. At 10 days out, GetMyWeather will be only 50 percent confident. After 10 days, the confidence range is significantly less than 50 percent.

The GetMyWeather API is easy to use.

# What do I need to use this API?

To use the API, you will need know simple HTML and Javascript syntax.

You will have to pay to use the API, but not much.

# How much does this it cost?

- First 100,000 calls/day: .01 cent per call
- 100,000 calls/day: contact us at 1-888-alan-getweather


# What type/kind of data does GetMyWeather return?

GetMyWeather provides four weather data points

# Parameters

Parameter | Returned value | Example
----------| ---------- | ---
Temperature |  A number that represents degrees Fahrenheit. | 72 means 72 degrees Fahrenheit
Wind speed | A number that represents kph (kilometers per hour) | 21 means 21 kph
Humidity | A number between 0-100 that represents a percentage| 80 means 80 percent humidity.
Precipitation | A number between 0-100 that represents a percentage| 50 means 50 percent chance of precipitation

# How do I make requests to GetMyWeather?

** Do more than tell developers what they can expect within those ranges.
'If you do this, this will happen. If you put too small of a location, you will get x returned.' I need to tell developers of the CONSEQUENCES of their calls for all the parameters. **





some users will not have lat long, so convert zip to lat long ie campers, or areas that change
