---
layout: page
title: "HTTP and RESTful APIs, Defined"
course: "webdev"
unit: 10
---
## HTTP and Statelessness
The World Wide Web is based on a protocol known as the _Hypertext Transfer Protocol_ (HTTP). You see this every time you go to a webpage because they all have the ```http://``` prefix (or ```https://``` in the case of encrypted traffic). When you visit a website, a few things happen to make what is called an _HTTP request_ to access a _Uniform Resource Locator_ (URL). Before HTTP requests are initiated, two things happen:
1. The hostname (```www.example.com```) is sent to a _Domain Name Resolution_ (DNS server). The DNS server sends back the IP address associated with the hostname. This IP address tells all of the servers on the Internet where a server is located.
2. Your computer receives the hostname and prepares the HTTP request.

An HTTP request is then prepared. The client (your computer) sends the HTTP _request_ to the web server. The HTTP request contains the request type (detailed below), _headers_, and a request body. An HTTP header contains information about your request and about you, including for example the _User Agent String_ - an identifier of the browser, version, and operating system that you are using. Headers can contain lots of other information, some of which we will explore in this chapter. We'll talk more about the request body for HTTP below. 

Once the request is sent to the server, the server processes it and sends back a _response_. The response also contains headers as well as a body, which is usually your HTML page, though in this chapter it is usually a JavaScript JSON object (JSON, short for _JavaScript Object Notation_ is a file format that JavaScript will parse into an Object). The third element is a status code. The one you're probably the most familiar with is the ```404``` error, which means that a URL could not be located. However, there are [lots of HTTP status codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status). A ```200``` status code is generated each time a web page is successfully requested and returned. ```200``` status codes generally mean "everything is good here", ```300``` status codes are sent when a user is redirected to another URL (i.e. every Bit.ly link returns a ```300``` status code - ```301``` _Moved Permanently_ to be exact - and the request body contains the new URL. The browser takes this and initiates a new, identical request to the new URL). ```400``` status codes are client-side errors, meaning the user asked for a page that doesn't exist or sent invalid data or doesn't have access to a file. By contrast ```500``` errors indicate server-side errors, meaning something on the server is broken and can't fulfill the request.

HTTP is an inherently _stateless_ protocol. Statelessness means that each HTTP request/response pair is treated like the only one. The server doesn't know any requests from the client that came before and assumes no requests will come after. While this sounds like it could be problematic on the modern web where we log in to things, it made a lot of sense in a historical context. Relying on the user's IP address poses many problems - in the olden days, Internet connections were inconsistent so an IP address could change or a user could be disconnected between requests. Statelessness prevents that from becoming a problem and also enables things like...you accessing the same website from your laptop and your phone without the web server sending the wrong thing to the wrong device. Statelessness also allows two other features unique to HTTP - _proxying_ and _caching_. Proxying allows a "man-in-the-middle" that can relay HTTP requests on behalf of a client (for example, a school content filter) and caching allows content to be stored locally and reused instead of downloading it from the web server each time it is needed. 

However, over time, websites became dynamic. All rendering of HTML, CSS, and JavaScript happens on the client-side. However, many websites receive data from code that lives on servers and in forms that are submitted and processed by these apps (i.e. Google Docs, PayPal, etc.). These types of tools don't benefit from statelessness because they depend on user data being persistent between each request. Enter: _cookies_. A cookie is a small piece of data that is sent as a header in an HTTP response and then is sent back to the server by the browser with each subsequent HTTP request. Typically this is a unique hexadecimal number created by doing math on a random string of characters and the current date and time. The date and time are used to avoid _collisions_, a situation where two users would have the same ID meaning browsers would send the wrong data to the wrong device. By sending this data as a HTTP header, a web server application can associate a session and the data from that session with the correct user even if an Internet connection is inconsistent or unstable. 

## APIs and REST
So you may be asking yourself at this point why we're learning about how the web works. The answer is that JavaScript and websites use HTTP as a tool to send data objects back and forth. You may recall from the last unit and other times where I've said that JavaScript rewrites the DOM in real-time. However, sometimes it needs to get data from websites in order to do that. For example, consider a website where you type in a zip code to get a weather forecast. In order for the JavaScript to be able to rewrite your page, it needs to get the weather data from an authoritative source.

In the last unit, we talked briefly about _Application Programmer Interfaces_ (or APIs). Last unit, we looked at tools like Desmos and Reveal.js where the API gave us a set of client-side tools that we could use. This week we will look at _RESTful APIs_. _REST_ stands for _Representational State Transfer_ which means that it uses HTTP statuses, headers, and message bodies to transfer data to and from server applications. In the olden days, getting data from other websites involved special protocols or proprietary formats. RESTful APIs use the tools built-in to the HTTP protocol for transferring data.

When sending a RESTful request, the request type is used to identify what the server application is supposed to do with the request. Up above, we talked about the HTTP request type. The request type tells the receiving server how to interpret the data that it's receiving and what to send the client as a response. All web requests when you go to a website typically will use a request type of ```GET``` which literally means "get this page". But there are other types that tell the server to process the request differently. RESTful APIs use a few of them:
* ```GET```: Get data from an API
* ```POST```: Tell the API to add new data
* ```PUT```: Tell the API to replace data with this new data
* ```PATCH```: Tell the API to make updates to data
* ```DELETE```: Tell the API to delete some data

The request header may include an _API Key_. RESTful APIs use keys for two primary purposes. The first is to authenticate your request as coming from you. The second is for billing - APIs are typically services and not all of them are free. Some will bill you if you make more than a certain number of API requests (some will also cut your service off until some time period has elapsed). HTTP headers are also used to send other data like pagination (some APIs will only send back a certain number of rows, and pagination can be used to get multiple pages of data). 

In a RESTFul web API, the body of the request is a JavaScript object. 

The HTTP response uses HTTP similarly. HTTP status codes are used to indicate if any errors occurred (like any page, it will return a ```200``` series response if everything is good or a ```400``` or ```500``` error if something is wrong). The response body will contain a JavaScript object with the data requested (and typically some metadata as well such as the number of records returned). On the next page we will put this process together completely and build a working API call.

## JSON
I've mentioned JSON a few times. JSON, short for JavaScript Object Notation, is a way to take JavaScript objects and arrays and convert them into a text format that can be transmitted via HTTP or stored in a file. [JSON uses curly braces for objects and brackets for arrays](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON) and can store complex data structures as a text block. A simple object would be something like this:

	{ 'name': 'Mark Samberg' }

You could store this in a variable, i.e.

	var person = { 'name': 'Mark Samberg', 'institution': 'North Carolina State University'}

In your JavaScript, you could reference variables ```person.name``` and ```person.institution``` to get at this data like any object. 

A more structured example may look like this:

	var person = {
	  "firstName": "Jonathan",
	  "lastName": "Freeman",
	  "loginCount": 4,
	  "isWriter": true,
	  "worksWith": ["Spantree Technology Group", "InfoWorld"],
	  "pets": [
		{
		  "name": "Lilly",
		  "type": "Raccoon"
		},
		{
		  "name": "Spot",
		  "type": "Cat"
		}
	  ]
	}

You'll see the item ```pets``` which is an array containing Jonathan's pets. Within each element of the pets array is an object containing a name and a type. therefore, the code:

	for(var i = 0; i < person.pets.length; i++){
		console.log(person.pets[i].name + " the " + person.pets[i].type);
	}

would output:

	Lilly the Raccoon
	Spot the Cat