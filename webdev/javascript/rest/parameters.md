---
layout: page
title: "APIs with Parameters"
course: "webdev"
unit: 10
---
In the previous examples, the APIs didn't need to be sent with a request body, since everything could be done with a URL. Not all APIs work like that. The [WeatherBit API](https://www.weatherbit.io/api/weather-current) for example uses parameters in the request body. You may notice in the API specifications that the parameters to get the weather for a zip code or a place that they are listed in the spec as being in the URL. However, notice the URL in the demo:

	https://api.weatherbit.io/v2.0/current?lat=35.7796&lon=-78.6382&key=API_KEY&include=minutely

A question mark in a URL separates the URL from a second part of the URL known as the _query string_. The query string encodes parameters in the request body as a part of the URL so that they can be passed by services that don't support passing parameters in the request body. jQuery and JavaScript, along with the API, are smart enough to work that out. Therefore, in our ```$.get()``` request, we now use _two_ parameters: one with just the URL before the query string (```https://api.weatherbit.io/v2.0/current```) and another containing an object that contains all of the parameters that are required in the query string. This also allows us to construct our request without having to do a lot of string manipulation in JavaScript like we had to do to construct a custom URL for the dictionary service. The URL is always the same and the data in the object will change, and objects are easy to manipulate in JavaScript.

## API Keys
Many API services use _API Keys_ to uniquely identify the user or application behind each request. The reasons for this are multifold:
* Prevents abuse of the service by limiting the number of requests a single user can send in any given time.
* Allows for billing. Not all APIs are free or freely available. Some APIs have a free tier (like the WeatherBit API), some charge per API call (or usually per thousand calls), and others charge in usage tiers. 
* Can be used to encrypt data or tie data to the source.

Typically you have to register for a key and want to keep the key secure and not post it to GitHub. For JavaScript apps, this can prevent security issues and there are ways to prevent this that we will talk about in the next unit. For this unit, the important things to know is that if you register for an API key, **do not enter a credit card number** and only use free tiers. Since you'll have to expose the API key publicly you don't want an API that can bill you.

## WeatherBit Example

In the WeatherBit CodePen below, I have a hidden error. We're keeping the error generic because I couldn't find documentation on WeatherBit's error reporting. We also have a form where someone can input the ZIP Code and a table that's hidden with the weather data. In the JavaScript, I have a catch when the form is submitted and ```event.preventDefault();``` to keep the page from redirecting. I set up the parameters object. Note that while I hard code my API key, units, and country - these could all be taken in programmatically from the form. I do set the ZIP code from the form, and then I make the API call. When it succeeds, I hide the error, populate the table, and show it. If it fails, I hide the table and show the error. Unlike the previous examples, the response is returned as an array within an object, so I have to pull out the object and then the first element from the array.

<p class="codepen" data-height="600" data-theme-id="dark" data-default-tab="result" data-user="mjsamberg" data-slug-hash="LYxyMYe" style="height: 600px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Unit 10 - Weather API">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/LYxyMYe">
  Unit 10 - Weather API</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## More Complex Example
Take a look at this example using the [Google Civic Data Information API](https://developers.google.com/civic-information/docs/v2/representatives/representativeInfoByAddress). Can you figure out how it works?

<p class="codepen" data-height="600" data-theme-id="dark" data-default-tab="js,result" data-user="mjsamberg" data-slug-hash="mdRmaLY" style="height: 600px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Unit 10 - Google Civic Data Information">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/mdRmaLY">
  Unit 10 - Google Civic Data Information</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>