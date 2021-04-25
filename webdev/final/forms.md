---
layout: page
title: "Forms and Form Validation"
course: "webdev"
unit: 13
---

We've done a lot of work in previous units with HTML forms, but haven't explored them in-depth beyond using them as vehicles to get input to and from JavaScript. Before we wrap up for the semester, I want to take a deeper dive into HTML forms. Whether it looks like a proper form or not, anywhere you input data on a website - from a search box to a radio button - is an HTML form. [Bootstrap](https://getbootstrap.com/docs/4.1/components/forms/) has some ways to style them built in, and there are a number of other CSS and [JavaScript](https://bashooka.com/coding/javascript-libraries-for-amazing-and-functional-forms/) libraries that can help with the appearance and the functionality of your forms. 

## HTML Forms
While we've been using a select few types of form fields so far, there are a wide variety of [form field types](https://www.w3schools.com/html/html_form_input_types.asp) available. These typically use the [```<input>```](https://www.w3schools.com/tags/tag_input.asp) tag. Browser support for the different types of fields will differ. For example ```<input type="date">``` may display a date picker in some browsers and validate for correct dates, while it may not in others. ```<input type="tel"  placeholder="123-456-7890" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}" >``` may let users input a telephone number and validate it, but in other browsers, it may not.

While most form fields use the ```<input>``` tag, some the ```<textarea>``` tag can be used for longform text input. ```<textarea>``` has [several options](https://www.w3schools.com/tags/tag_textarea.asp) to control the way the textarea box works, but it's always a large, empty box. You can include JavaScript like [TinyMCE](https://www.tiny.cloud/blog/bootstrap-wysiwyg-editor/) to get a formatting toolbar in ```<textarea>```s.

The other option is the ```<select>``` tag, which allows you to create a drop-down menu. Within selects, you'll find the ```<option>``` tag. The option tag has two attributes, ```selected``` and ```value```. ```selected``` indicates that it's the default option for the ```<select>```. ```value``` is the data that is sent by the form (for example, you may display state names on the screen, but store the abbreviation). For example:

	<select name="state" id="state">
		<option value="NC" selected>North Carolina</option>
		<option value="SC">South Carolina</option>
	</select>

All form objects need two attributes ```id``` and ```name```. ```id``` is used for reference on the page in JavaScript. ```name``` is what is sent to the form when it's submitted. The value for ```id``` and ```name``` are typically the same, for example ```<input type="text" name="username" id="username">```. The only difference is in radio buttons or checkboxes. Each option in a radio button or checkbox needs the ```name``` name but a different ```id```. It's a little confusing, but the ```id``` attribute is used in JavaScript and to tie an ```<input>``` to its label. The ```name``` is used to choose the value that's sent with the form when selected. Radio buttons and checkboxes also take a ```value``` attribute which is the value that will be stored. For example:

	<div>
		<input type="radio" id="bbq_vinegar" name="bbq" value="vinegar">
		<label for="bbq_vinegar">Vinegar</label>
	</div>
	<div>
		<input type="radio" id="bbq_tomato" name="bbq" value="tomato">
		<label for="bbq_tomato">Tomato</label>
	</div>

yields:
<div>
<input type="radio" id="bbq_vinegar" name="bbq" value="vinegar">
<label for="bbq_vinegar">Vinegar</label>
</div>
<div>
<input type="radio" id="bbq_tomato" name="bbq" value="tomato">
<label for="bbq_tomato">Tomato</label>
</div>

Unlike APIs, forms typically aren't _asynchronous_ - the redirect you to another URL when you submit the form. We've been overriding this behavior by including ```event.preventDefault();``` in our jQuery. The ```<form>``` tag has two other attributes that are typically used in _synchronous_ actions: ```method``` and ```action```. ```method``` accepts two values: ```GET``` and ```POST```, which like in JavaScript define how the request will be sent to the script that's processing the form (recall from last unit that ```GET``` builds a _query string_ in the URL, whereas ```POST``` is designed to add new data and everything is transmitted as HTTP data). ```GET``` is typically avoided because the data sent is exposed in the query string, so entering a password in a form that's using a ```GET``` request is insecure. Therefore, for security and fidelity to the idea that ```GET``` is for retrieving data only, **```POST``` is the recommended best practice for all forms**. The second attribute ```action``` describes the URL where the data in the form should be sent. 

Example ```<form method="post" action="http://www.my.website/formsubmit">```. Because form actions are synchronous, you will be redirected to the page in ```action``` when the page is submitted.

Let's look at this in action. Here is a simple contact form using a service called [FormSpree](https://formspree.io), which allows you to make forms that are stored in a database.

<p class="codepen" data-height="550" data-theme-id="dark" data-default-tab="html,result" data-user="mjsamberg" data-slug-hash="zYNMRdz" style="height: 550px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Formspree Email Demo">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/zYNMRdz">
  Formspree Email Demo</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>


## Asynchronous Submission
There are also times where you want form posts to happen asynchronously without redirection - for example, if you want the user to stay on the current page, or use their form data in multiple ways. In that case, you can use your jQuery ```$.post()``` commands to submit the form. Instead of ```$.done()``` and ```$.fail```, since we're not processing an API, we use ```$.then```. ```$then``` takes two arguments - a function for when the call succeeds and another for when it fails. 

For example, instead of redirecting to the FormSpree submit page, this example uses jQuery to submit the contact form data and then display a [Bootstrap Modal](https://getbootstrap.com/docs/4.1/components/modal/) when it's completed. The ```ajaxSetup``` sends an HTTP header to let FormSpree know we will be sending JSON through an API instead of a typical HTTP post request.

<p class="codepen" data-height="550" data-theme-id="dark" data-default-tab="js,result" data-user="mjsamberg" data-slug-hash="abpXydX" style="height: 550px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Formspree AJAX Email Demo">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/abpXydX">
  Formspree AJAX Email Demo</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## JavaScript Validation
Many of the JavaScript libraries can also help with form validation. There are two types of form validation, _client-side_ and _server-side_. Client-side validation is what we've been doing so far - checking for errors in JavaScript before the form is submitted. Adding a ```required``` attribute to any field is the most basic validation, but other _client_side_ validation is in JavaScript. _Server-side_ is where the API checks for errors and returns a ```500```-series error. 

So far, we've used ```event.preventDefault()``` in order to let JavaScript handle the forms instead of submitting it. However, without ```event.preventDefault``` the form would submit. However, you can include things that happen before the form submits. For example, you can check the values in form fields. Adding ```return false``` in the validation function would stop the form from submitting. No action or ```return true``` allows the form to submit as usual. See for example:

<p class="codepen" data-height="550" data-theme-id="dark" data-default-tab="js,result" data-user="mjsamberg" data-slug-hash="XWpOewp" style="height: 550px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Formspree Validation Demo">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/XWpOewp">
  Formspree Validation Demo</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
