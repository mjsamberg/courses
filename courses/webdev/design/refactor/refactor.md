---
layout: page
title: "Refactoring"
course: "webdev"
unit: 12
---

In computer science, the term _refactoring_ means to clean up code and reduce redundancy without impacting the functionality or appearance of an application. In web development, this typically means doing a few things:
* Ensure your correct header and ordering
* Ensuring your code is properly indented and formatted
* Ensuring you're running the latest version of Bootstrap and jQuery
* Removing unused CSS
* Combining identical CSS classes or using inheritance to minimize the amount of CSS used

## Correct header and ordering

Order matters in CSS and in JavaScript. When including CSS files, Bootstrap should always be first, followed by custom CSS for any other frameworks or libraries you're using, followed by your site-level custom CSS. With JavaScript, jQuery should always be first, followed by any custom libraries or frameworks, followed by your own custom ```.js``` files. CSS should be included in the ```<head>``` tag right before you close the tag (```</head>```). JavaScript should be the last thing included in your page right before ```</body>```.

Remember that all of the content that is displayed to the user should also be between ```<body>``` and ```</body>```. This means a starter template should look like this:

	<!DOCTYPE html>
	<html lang="en">
		<head>
			<title>Welcome to my Virtual Terrarium</title>
			<meta charset="utf-8" />
			<meta http-equiv="X-UA-Compatible" content="IE=edge" />
			<meta name="viewport" content="width=device-width, initial-scale=1" />
			<!--Add Bootstrap code here-->
			<!--Add custom CSS libraries and frameworks here-->
			<!--Link to your site's custom CSS here-->
		</head>
		<body>
			<!--All content that displays to the user goes here-->
			<!--Add jQuery here-->
			<!--Add custom JavaScript libraries and frameworks here-->
			<!--Link to your site JS here-->
		</body>
	</html>

## Indenting and Formatting
In HTML, everything inside of any container should be indented 2-4 spaces if the container spans multiple lines. This promotes readability. In addition, text may be broken up into multiple lines.For example, consider this bad example:

	<div class="container">
	<section>
	<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
	</section>
	<section>
	<ul>
	<li>Eggs</li>
	<li>Milk</li>
	</ul>
	</section>
	</div>

It's difficult in this example to determine where containers start and end, and what's in the containers. By indenting, we can improve readability and it's very easy to see if your closing tags are out of order or not nested properly. 

	<div class="container">
		<section>
			<p>
				Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
			</p>
		</section>
		<section>
			<ul>
				<li>Eggs</li>
				<li>Milk</li>
			</ul>
		</section>
	</div>

In JavaScript, similar rules apply. This code is valid, but is hard to read:

	$document.ready(function(){
	$("form").submit(function(){
	for (var i=0; i<array.length; $i++){
	alert("hello");
	}
	})
	})

Indenting container elements (things within curly braces ```{ }```) improves readability:

	$document.ready(function(){
		$("form").submit(function(){
			for (var i=0; i<array.length; $i++){
				alert("hello");
			}
		});
	});
	
## Updating Bootstrap and jQuery
Bootstrap and jQuery are active development projects and are updated relatively frequently. While updating Bootstrap and jQuery does require testing in large sites, updating can fix some bugs.

**If you're using uncustomized bootstrap**, the Bootstrap site [houses the latest versions](https://getbootstrap.com/docs/4.6/getting-started/introduction/) using the version selector in the top right. Version 5 is currently in Beta, so use version 4.6. Replace your Bootstrap CSS and JavaScript using the code provided.

**If you're using Bootstrap.build**, the Bootstrap version will be updated when you republish your custom theme to CDN. Use the JavaScript from the Bootstrap website above.

To update jQuery, go to the [jQuery CDN page](https://code.jquery.com), click on "Minified" under the latest version of _jQuery 3.x_ and copy the code that appears. Replace the jQuery line in your page with the new code.

## CSS Cleanup
To keep your CSS clean, remove any CSS that's not being used to style part of your website. Also, refactor to eliminate duplication. For example, instead of having this in your CSS/HTML:

	.my-paragraph{
		color: blue;
		font-size: 18px;
	}
	
	.my-other-paragraph{
		font-size: 18px;
	}
	
	<p class="my-paragraph">Text</p>
	<p class="my-other-paragraph">Text again</p>

Leverage the power of CSS to do things like the following. While not necessarily shorter, it eliminates complexity, and creates fewer places things need to change in the event that you want to change font sizes down the road.

	.large-paragraph{
		font-size: 18px;
	}
	
	.text-blue{
		color: blue;
	}
	
	<p class="large-paragraph text-blue">Text</p>
	<p class="large-paragraph">Text again</p>
	
