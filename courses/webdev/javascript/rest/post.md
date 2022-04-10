---
layout: page
title: "POSTing to RESTful APIs"
course: "webdev"
unit: 11
---
In the last unit, we looked at getting data from RESTful APIs. While there is a lot of good data to get and add to your page, the true interactivity of pages involves being able to trigger actions that _store_ data, as well as _retrieve_ it. In the last unit's RESTful overview, we learned that there were multiple types of ways to post HTTP requests. While all web requests use ```GET```, we can use ```POST```, ```PUT```, ```PATCH```, and ```DELETE``` in order to trigger the RESTful API to store or modify data. **You'll need to read the API documentation to determine how to use different request types.** While there are standards for RESTful APIs, each tool operationalizes them slightly different. So while APIs may all be accessed the same way, they're all slightly different in how they accept data, and how they return data. 

## A quick note about HTTP authorization
In most of the APIs we looked at last week, the APIs were sent as a parameter or as a part of the URL. While most APIs work this way, not _all_ of them do. Some will use an HTTP header with the token stored inside of it, and some will use a technology called OAUTH tokens. An OAUTH token allows users to log in with their own credentials and interact with their own data (i.e. a Google account) in a way that keeps data with the user. OAUTH tokens are a bit more complicated to implement (and beyond what we'll cover in the course) and are done differently based on the tool. For example, [see the Google tutorial](https://developers.google.com/identity/protocols/oauth2/javascript-implicit-flow).

However, tools that use HTTP headers to transmit API keys are actually quite easy to implement. If the API documentation requires a header for the authorization key, here's the code you use. **Note that you'll have to check the documentation to get the header name and key name right.** 

	$.("button").click(function(){
		$.ajaxSetup({
		  headers: {
		  	'Authorization': "Put the token value here as provided by the documentation",
		  }
		});
		
		//Rest of your Javascript here including your GET/POST/PUT/PATCH/DELETE requests and response handling.
	});


## Examples
Some writeable requests in jQuery look just like ```GET``` requests. Any ```POST``` request just uses ```.post()``` instead of ```.get()```. ```PUT```/```PATCH```, and ```DELETE``` requests work a bit different. 

Instead of something like:

	$.post("http://url", dataObject)

	$.ajax("http://url", {"type": "PUT", "data": dataObject});

Everything else works the same including the use of ```.done()``` and ```.fail()````. 

### JSONBin

For the first example, we will use a tool called [JSONbin.io](https://www.jsonbin.io). This tool allows you to store JSON objects from your site for retrieval and reuse between sessions. For this example, I will use this tool to create a simple shopping list. See the Codepen below. First, as soon as the document initializes, it issues a ```GET``` request without any user interaction in order to pull the JSONbin down in the current state and draw the table. The global variables at the top of the document contain the bin ID in JSONbin and the listItems. Because it's a public Bin, no API key is required. Once I get the JSONbin contents down, I store them in my ```listItems``` variable, and show the shopping list. Since I'll be recreating my shopping list at multiple different points, I have moved all of the code to create the shopping list into the ```showList``` function. When you want to update the JSONBin, you simply need to issue a ```PUT``` request to the JSONBin API with the new JSON object that should overwrite the old one. So I have a single function, ```updateList``` that does this and updates the list accordingly. I also have handlers to add new items and delete a single checked item via radio button. These update the ```listItems``` array and call my ```updateList``` function to save the changes. Inside of update list we wrap the ```listItems``` array using ```JSON.stringify()```, which is a helper method in JavaScript that cleans up our JSON object before sending. 

<p class="codepen" data-height="800" data-theme-id="dark" data-default-tab="result" data-user="mjsamberg" data-slug-hash="LYxeqLL" style="height: 800px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Unit 11 Shopping List">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/LYxeqLL">
  Unit 11 Shopping List</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>


### ClickSend
ClickSend is an API that can send emails or SMS messages. In this example, we will send an SMS. For security reasons, I'm leaving the API out of the CodePen so people who stumble across the CodePen can't spam anyone. The API key is ```bWpzYW1iZXJAbmNzdS5lZHU6MjNFMUJEODItMDgwOS03RTkyLTAzNkYtOTQ3OEMzOUZGMDRD```. [ClickSend's documentation](https://developers.clicksend.com/docs/rest/v3/?java#send-sms) states that the request body must contain an array of messages, each element of the array containing an object with a ```source```, ```body```, and ```to``` defined. It also needs an authorization token in the header containing the API key.

<p class="codepen" data-height="400" data-theme-id="dark" data-default-tab="js,result" data-user="mjsamberg" data-slug-hash="yLgprpR" style="height: 400px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Unit 10 ClickSend">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/yLgprpR">
  Unit 10 ClickSend</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>



### IFTTT
One of my favorite web services is called [IFTTT](https://www.ifttt.com). Short for "If this, then that", IFTTT allows you to connect applications to activate functions in one application when something happens in another. Their solution is "no code" - everything is drag-and-drop and you don't need to be able to code to use it. _However_ one of their core services is a WebHook service. Below are two examples. One is a button that, when clicked, will turn on the light in my home office. While you can include three values in your request body in the form of ```{value1: xyz, value2: xyz, value3: xyz}``` (object keys cannot be changed). See [the documentation](https://maker.ifttt.com/use/demo).

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="js,result" data-user="mjsamberg" data-slug-hash="qBRpwVE" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Unit 11 IFTTT Light">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/qBRpwVE">
  Unit 11 IFTTT Light</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

