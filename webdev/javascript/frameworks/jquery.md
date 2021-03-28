---
layout: page
title: "JavaScript Libraries and JQuery"
course: "webdev"
unit: 9
---
In the last unit, we reviewed JavaScript. JavaScript is an incredibly powerful language with a lot of capability and function. To make JavaScript easier to work with, _libraries_ are used. A library is a pre-made set of commands that can be included in your JavaScript. These are typically shortcuts where others have written functions for you that you can include in your JavaScript. Contrast this with _frameworks_ which tend to have more "opinions" - there are helper functions in the JavaScript, but also concrete methods for how they need to be implemented. Bootstrap is an example of a framework - Bootstrap has helper classes, but also very specific opinions about how they should be implemented. JavaScript libraries **augment** JavaScript, meaning that they utilize JavaScript to add additional features that are easy to use. Everything a library does can be done manually by writing the JavaScript by hand, but the libraries just save time (jQuery, for example, is tens of thousands of lines of code that don't have to be manually written).  

## Adding JavaScript to HTML
Before we begin discussing writing JavaScript, we have to actually talk about file structure. Like CSS, JavaScript can be written inline, or it can be placed in a separate file. For example, you can include JavaScript in a ```<script>``` tag as follows:

	<script language="JavaScript">
		console.log("Hello world!");
	</script>

Alternatively, you can create a new file that just contains your JavaScript code. For example, if I have a folder called ```js``` and a file inside of it called ```scripts.js```, I could link it from my HTML using the code 

	<script language="JavaScript" src="js/scripts.js"></script>

And in my ```js/scripts.js``` file, I would have all of my JavaScript code, i.e.

	console.log("Hello World!");

Scripts are always placed at the bottom of an HTML file before the ```</body>``` tag. 

## HTML Forms
Much of the interactivity on webpages comes from HTML forms. Forms have a few [input types](https://www.w3schools.com/html/html_form_input_types.asp), mainly types of text, radio buttons and select dropdown boxes (_select one_) and checkboxes (_select many_). [Bootstrap has a lot of form styling](https://getbootstrap.com/docs/4.1/components/forms/) built in. Note that by default the ```<button>``` command will submit the form (more on that next week in APIs). If you want the button to be attached to JavaScript instead, use the ```type="button"``` attribute, adding classes as needed. Example:

	<button type="button" class="btn btn-large btn-primary">Large Button</button> 

## jQuery
The most common JavaScript library is called [jQuery](https://api.jquery.com). While jQuery is an older tool and everything can be done solely with JavaScript commands, JQuery gives us useful shortcuts to make a lot of DOM manipulation tasks easier. jQuery allows you to edit text and attributes, hide and show objects, and more with very simple commands. 

For example, if I wanted to hide all elements with the class ```.hideme``` using regular JavaScript, I'd have to write the following code:

	var elements = document.getElementsByClassName('hideme');
	for (var i = 0; i < elements.length; i++){
		elements[i].style.display = 'none';
	}

whereas in jQuery, the only code I'd need is this:

	$(".hideme").hide();

Like Bootstrap, most JavaScript libraries are loaded from a _Content Distribution Network (CDN)_, which is a fast server on the Internet that serves up content for people to consume. jQuery is loaded in most Bootstrap install templates (search your pages to ensure it's already loaded). If you don't already have it, it's added by including the script from CDN:

	<script src="https://code.jquery.com/jquery-3.6.0.js" integrity="sha256-H+K7U5CnXl1h5ywQfKtSj8PCmoN9aaq30gDh27Xc0jk=" crossorigin="anonymous"></script>

All jQuery commands start with ```$("selector")``` where ```selector``` is a CSS selector either tag, a class ```.class``` or an element with an ID ```.id```. All of your jQuery is wrapped as follows:

	$(document).ready(function(){
		//jquery goes here
	});

This ensures that the jQuery script is loaded and the page has fully rendered before commands try to execute. If jQuery isn't already loaded, your script will fail. Inside your jQuery, you can attach functions to events like when an element is clicked, or a keypress is made, etc.

Typically a jQuery handler will follow the format:

	$("selector").text(function(){
	
	});
	
where ```selector``` is your CSS selector and ```text``` is the event or action you want to take. As you recall from last week, the word ```function``` defines a JavaScript function, and is used to create a new function that will happen when an event happens. Other jQuery events may look like this

	$("selector").action();

where ```selector``` is your CSS selector and ```action``` is the action you want to perform. Some actions may take mandatory or optional arguments, but the [documentation provides examples](https://api.jquery.com) for each use.

Take a look at the example below. There are several interactive elements. The button on the page toggles the visibility on the form. The name field changes the header when you type something in and leave the field. The number field is validated when you toggle out of the field and uses Bootstrap classes to provide feedback. The Header Color field toggles Bootstrap classes for the header. The ```aria-live``` attribute is used to [define a region where the text may change](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Live_Regions). Note that when we take these actions, it's referred to as **DOM Manipulation**. JavaScript changes the DOM on the page, or in layman's terms - it rewrites parts of the page in real time.

<p class="codepen" data-height="600" data-theme-id="dark" data-default-tab="js" data-user="mjsamberg" data-slug-hash="mdOZBpa" style="height: 600px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Unit 9 - JQuery">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/mdOZBpa">
  Unit 9 - JQuery</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

Here is another example, using jQuery and JavaScript to build a simple calculator:

<p class="codepen" data-height="500" data-theme-id="dark" data-default-tab="result" data-user="mjsamberg" data-slug-hash="eYgOOpO" style="height: 500px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Unit 9 - Calculator">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/eYgOOpO">
  Unit 9 - Calculator</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>