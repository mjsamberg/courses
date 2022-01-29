---
layout: page
title: "Intro to JavaScript"
course: "webdev"
unit: 8
---
Interactivity on webpages comes in two forms: client side and server side. Server-side interactivity happens when you submit a form or click a link, content is generated dynamically on the server, and sent to the client. Examples of this occur every time you do a Google search or shop online - the content that is displayed exists in a database, is selected in real-time, and sent to you as webpage. Typically with server-side interactivity, a page will refresh with new data.

Client-side interactivity occurs every time a web page changes without reloading. When you click on something and a page changes dynamically, or when you scroll down and new content appears, or when you use something like a dropdown menu - these are all examples of client-side interactivity. They may fetch content from servers (more on that in a few weeks), but all of the rendering happens in the browser on the user's local machine.

JavaScript is the programming language that makes client-side programming possible. JavaScript was started in 1995 with the express intent of creating dynamic web pages. However, it has exploded in popularity in the past 20 years, now powering mobile apps, desktop apps, even server software. JavaScript is referred to as a _scripting_ language, meaning that it is used to write smaller scripts that are typically executed in a linear fashion (though, not really, and we will get there). JavaScript is also _just-in-time compiled_, meaning that the browser interprets the code as it needs it (unlike, say, an app on your phone, which is distributed with all of the instructions pre-compiled for the phone to interpret). 

JavaScript is an incredibly powerful programming language with a lot of helpful tools built-in. JavaScript is also extended by a number of frameworks, such as JQuery (next week), that add functionality to JavaScript. 

On a webpage, JavaScript works by rewriting the HTML on the page. Recall the DOM Model from unit 1 (here it is again):

Web pages are structured according to the _Document Object Model_ (DOM). 
<div class="text-center">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/DOM-model.svg/1200px-DOM-model.svg.png" alt="Document Object Model" style="max-width: 50%;">
</div>

The DOM is a fancy way of saying that elements contain attributes and text, but may also contain other attributes. Elements that are within elements must be completely contained in the element. For example, if we wanted our "Go to Google!" link to be emphasized with some text after it, we would need to contain the ```em``` tag completely within the ```a``` tag. Therefore, this is valid:

	<a href="http://www.google.com"><em>Go to Google</em></a> <em>and search because Google is a search engine.</em>

and this is valid:

	<em><a href="http://www.google.com">Go to Google</a> and search because Google is a search engine.</em>

however, this HTML is not valid:

	<a href="http://www.google.com"><em>Go to Google</a> and search because Google is a search engine.</em>
	

Because HTML has this predictable structure of element -> attributes -> content, JavaScript can rewrite this content in real time, adding CSS classes to a link to change the appearance, changing the content of an element, etc. 

## Learning JavaScript
JavaScript is very similar to other programming languages. If you're familiar with programming, you'll probably catch on pretty quickly. This week we will focus on learning the basic syntax of JavaScript (and most other programming languages). Next week, we will begin to apply them to HTML.

### Assignment
* Go to [Free Code Camp's JavaScript Tutorial](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#basic-javascript)
* Create an Account
* Complete the Introduction to JavaScript Course - **You only need to do the basic JavaScript (111 Lessons)**
* Upload a PDF of the assignment list with the checkmarks. 
