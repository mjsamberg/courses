---
layout: page
title: "Getting Started with CSS"
course: "webdev"
unit: 4
---
## CSS Locations

Before we can write any CSS, we need to understand how it works and where to place it. CSS code can exist in three locations. The first is within a ```style``` attribute on any element. While doing this is **not a best practice** because the goal of CSS is to facilitate consistency across an entire site, it is necessary in some GUI-based websites (i.e. Canvas, Wordpress), where none of the other options will work. This would look like the following and the CSS included would yield link text that is in italics.

	<a href="http://www.ncsu.edu" style="font-style: italic;" target="_blank">

The second option is in a ```<style>``` element located within the head tag of a page. Again, this is not a recommended best practice, but is sometimes unavoidable. This code would make all links on the page italic:

	<!doctype html>
	
	<html lang="en">
	<head>
	  <meta charset="utf-8">
	
	  <title>The HTML5 Herald</title>
	  <style>
	  	a {
		  font-style: italic;
		  }
	  </style>
	
	</head>
	
	<body>
	</body>
	</html>

The **best practice for CSS** is to place all CSS in a separate file (with the extension .css) and then use the ```link``` element in the ```head``` tag. For example, suppose we have a file ```css/stylesheet.css" with the following contents:

	a {
		font-style: italic;
	}

We would include that in our web page by adding the following code to our ```head``` tag. 

	<link rel="stylesheet" href="css/stylesheet.css">

This tells the browser that we want to link in a stylesheet, and that the location is ```css/stylesheet.css```. Because of inheritance (discussed below), you can link in as many stylesheets as you want, and the URL in the ```href``` attribute can be a relative or absolute URL.

## CSS Code Layout
All code in is structured the same. The element be styled, and then all of the CSS attributes contained in curly braces. Inside the curly braces, one attribute is listed on each line with the attribute name, a colon ```:``` and then the value for that attribute. For example:

	p{ 
		color: green;
	}
	
	a{
		text-decoration: none;
	}

In this example, we are setting the ```p``` element. We are using the ```color``` attribute to set the color of the text and the value of that ```attribute``` to green. This means that all text in any ```<p>``` element will be green.

In the ```<a>``` element, we are setting the ```text-decoration``` element to ```none```, meaning that our links will not be underlined. 


## CSS Selectors and CSS code basics
We've now set up our stylesheet and we need to prepare our CSS. CSS can be applied at three levels: at an _element level_ (every element), with _classes_ (some elements) or with *IDs* (exactly one element). 

### Element-Level
CSS can be applied at the element-level, meaning that CSS can be applied each time a tag appears. You do not have to do anything to the HTML for this to happen. For example:

	p{
		color: green;
	}

would make all text in any ```<p>``` element will be green. This would apply to **all** ```<p>``` elements.

### CSS Classes
A CSS class can be affixed to any HTML tag to indicate that is a special type of that element. CSS classes can be *semantic* (defines what the element is) or *presentational* (defines how the class should look). Classes are added to tags as an attribute in the tag, and should be all lowercase and only use letters and hyphens. For example:

	<h1 class="section-heading">Section Introduction</h1>
	<p class="large">
		My intro text goes here so I want it to be larger than the other text.
	</p>
	<p>
		This text will not be styled because it doesn't use the class name.
	</p>


In your CSS files, you use a ```.``` followed by the classname to indicate that the element to be styled is a class:

	.section-heading{
		color: red;
	}
	
	.large{
		font-size: 16px;
	}

Because I am styling at the class-level, only the ```<h1>``` with the ```section-heading``` class would be turned red and only the paragraph with the ```large``` class would be set to 16px. The rest of the page would be rendered as normal.

### IDs
An ID can be applied to exactly one element per page. For example, a page would only have one title, so an ID can be used to reference that specific element. Like a class, an ID is also an attribute in an HTML tag, and should be all lowercase and only use letters and hyphens:

	<h1 id="page-title">My Page Heading</h1>

In CSS, we use a pound sign (```#```) to reference IDs:

	#page-title{
		color: blue;
	}

### Summary
The biggest issue with setting up CSS is deciding whether to style at the element level, use classes, or use IDs. As a rule of thumb:
* If you want to style **all** occurrences of an element, add the CSS at the **element level**.
* If you want to style **some** occurrences of an element, use **classes**.
* If you want to style **exactly one** occurrence of an element, use an **ID**.


## Inheritance
Inheritance is one of the most confusing concepts in CSS, and is the place where the most errors are caused. Inheritance states that CSS is _additive_, meaning that as CSS is applied, styles applied at the element, class, and ID level will be combined.

For example, if I have the HTML

	<h1 id="page-title">My Page Title</h1>

and the CSS

	h1{
		font-size: 32px;
		text-decoration: underline;
	}
	
	#page-title{
		font-color: red;
	}

The text would be 32px, underlined, and red because CSS is going to apply both the element-level attributes and the ID-level attributes. Inheritance also applies to elements contained within elements. For example, if I have the following HTML:

	<div class="make-text-geen">
		<h1>My Green Header</h1>
		<p>My green paragraph.</p>
	</div>

and then the following CSS:

	.make-text-green{
		color: green;
	}

all of the text inside the ```div``` element would be green because that attribute gets passed down to all of the elements contained inside of the single ```div```. This means that CSS can sometimes be unpredictable. Using the browser's developer tools (detailed later in this chapter, can help you see which CSS styles are applied to an element).

CSS styles are processed in linear order - each ```link``` CSS is processed in order from top to bottom, followed by ```style``` elements in the ```head```tag, followed by ```style``` attributes of an element. All CSS will be applied unless it's overriden by a CSS attribute further down the processing order. For example, consider this HTML:

	<div class="make-text-geen">
		<h1>My Green Header</h1>
		<p class="make-text-red">My red paragraph.</p>
	</div>

with the following CSS:

	.make-text-green{
		color: green;
	}
	
	.make-text-red{
		color: red;
	}

The paragraph would be in red because it's overridden by a class further down. The ```!important``` flag would override everything, but it's use should be limited:

	.make-text-green{
		color: green !important;
	}

would make all of the text green, regardless of what is specified later in the file.

## Compounding and Pseudoselectors

While elements can only have one ID, they can have many classes to take advantage of inheritance in CSS. Classes are separated in your HTML attribute by spaces. For example:

	<h1 class="section-title text-underline">My Section Title</h1>

Would apply the properties of the ```<h1>``` element, but also the properties of both the ```.section-title``` and ```.text-underline``` classes.

CSS can also be extremely precise in selecting elements, and they can be combined in CSS as well. For example, consider this HTML 

	<section id="lunch-menu">
		<h1>Lunch Menu Title</h1>
	</section>

You can use CSS selectors in your CSS file to select *only* the ```h1``` in the ```#lunch-menu```:

	#lunch-menu h1{
		text-decoration: underline;
	}

The result would apply the underline decoration to the ```<h1>``` in the lunch menu, but nowhere else on the page.

Pseudo-selectors can also be used in css. For example:

	a:hover{
		font-weight: bold;
	}

can be used to make all links bold when you mouse over them.

**[Review this resource for a full list of CSS selectors](https://www.w3schools.com/cssref/css_selectors.asp)** and complete the _CSS Selector Tester_ activity on that page as well. 

## Grouping Selectors
If you want a single set of styles to apply to multiple selectors, you can group them on the same line, with a comma between them. For example, if I want all headings level 1-3 to be red, I can use the following:

	h1, h2, h3{
		color: red;
	}