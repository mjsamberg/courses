---
layout: page
title: "Retrieving Data from a RESTFul API"
course: "webdev"
unit: 10
---

We will start off with a very basic example of a RESTful web API. The [Cat API](https://docs.thecatapi.com) is an API that provides cat pictures, because if the Internet can be counted on for anything -- it's cats. The API call we are going to use returns a random cat picture each time it is accessed. 

You can go to [https://api.thecatapi.com/v1/images/search](https://api.thecatapi.com/v1/images/search) to see the JSON output of the API. You'll see, as indicated by the ```[]``` at the beginning and end, that the API returns an array containing an object.

Now let's bring this into practice. Take a look at the CodePen below. We have a button that will be used to trigger the API call and display the cat image. We use jQuery's ```$.get()``` method and pass in our URL. In future activities, we will pass in a response body, but there isn't one here - we just call the URL and get the response.

Once we get the response, we have to act on it. In JavaScript, RESTful web calls execute asynchronously. This is done so that actions aren't _blocking_ - if a site is down or slow, your site will continue to function until the the action (called a _promise_) completes. Therefore, we need additional methods. ```$.done()``` executes when the API call has completed (returns a ```200``` series result code), and ```$.fail()``` occurs if a ```400```-```500``` result code is received. We aren't worried as much about error conditions here, so we will just define a successful condition. 

So, in the CodePen, I've added an event when the button is clicked and I use ```.$get()``` with the URL for my API. Now I'm setting up my action for when the promise completes. ```$.done()``` takes a parameter, which in this case I am calling ```response```. Inside the ```$.done()``` function, the first thing I'm doing is creating a new variable, ```catData``` that takes the first element out of the array that gets returned, which is our cat object. Next, I'm showing the ```#cat``` block. Finally, I set the attribute ```src``` in the ```<img id="cat-img">``` image tag to the URL of the cat image that's provided by the URL.

<p class="codepen" data-height="500" data-theme-id="dark" data-default-tab="js,result" data-user="mjsamberg" data-slug-hash="LYxygNo" style="height: 500px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Unit 10 Example - Pen">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/LYxygNo">
  Unit 10 Example - Pen</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>


<h2>Dictionary Example</h2>
Here's another example. The [Unofficial Google Dictionary API](https://dictionaryapi.dev) allows you to input a word, and get back the definition simply by including everything in the URL:

	https://api.dictionaryapi.dev/api/v2/entries/<language_code>/<word>

Because we're likely working in English, we will use en_US for the code for United States English (this is a [standard from a list of language locales](https://saimana.com/list-of-country-locale-code/)). Adding a word (such as _technology_ in your browser will return a JSON object with the definition.

Take a look at ```https://api.dictionaryapi.dev/api/v2/entries/en_US/technology``` in your browser. You'll see the JSON object with the definitions, pronunciations, etc. 

 In the HTML, we have a form that asks the user to input a word. I also have an error box that is blank (and hidden) as well as a definition box that is also blank (and hidden). The definition box has a card with a header (where we will repeat the word) and a list group. Both are blank, and we will fill them in with jQuery later.

In the JavaScript, we will create a function that executes when the form is submitted using the ```.submit()``` handler. By default, a form will initiate a ```GET``` request to the same page (causing the page to refresh). Adding ```event.preventDefault();``` prevents this inside the function prevents this. Also inside the function, we will handle our API calling. The first step is to build our URL - take the API's URL and append our form input to it. Because we are simply reading data, we will send a ```GET``` request. Once again we will use ```$.get()``` in jQuery and both ```$.done()``` and ```$.fail()``` to define successful and failure events.

Both ```$.done()``` and ```$.fail()``` take a parameter, which in this case I am calling ```response```. This contains the body of the HTTP response which, if it's a JSON object, jQuery will automatically turn in to a JavaScript object. In the ```$.done()``` function, I am setting the title of the card to the word that was entered, and calling a helper function to write the definitions to a list group (this isn't necessary, but it's cleaner). Note that the API spec returns the object inside an array, so you have to pull off the first element first (you can tell that because the response body example starts with a ```[```). Not all APIs do this.

In ```$.fail()```, I am populating the error message. This API provides a good error message, so I'm just passing it through verbatim.

 <p class="codepen" data-height="600" data-theme-id="dark" data-default-tab="result" data-user="mjsamberg" data-slug-hash="zYNwOmg" style="height: 600px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Unit 10 - jQuery Basic REST Dictionary Example">
   <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/zYNwOmg">
   Unit 10 - jQuery Basic REST Dictionary Example</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
   on <a href="https://codepen.io">CodePen</a>.</span>
 </p>
 <script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>