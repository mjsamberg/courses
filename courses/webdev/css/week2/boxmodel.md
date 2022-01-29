---
layout: page
title: "CSS Layouts and the Box Model"
course: "webdev"
unit: 5
---
Last week, we looked at using CSS to style our text. However, we can use CSS to do much more than just style text. CSS can also be used to arrange content on the page. In this unit, we will explore content layout using CSS, using responsive design features in order to change the way our web pages look on a desktop versus on a mobile device.

The most important thing to remember as we move through this unit is that **every element in HTML is surrounded by an imaginary rectangle**. Positioning in CSS, fundamentally, is controlling the size and location of that rectangle, and the whitespace surrounding it. 

## Inline vs. Block Elements
Unless otherwise specified based on our discussions later in the unit, some of these imaginary rectangles take up the entire width of the page regardless of how much content is located in them. These elements are referred to as ```block``` elements, and contain most of our semantic containers (```<div>```, ```<section>```, ```<article>```, etc.) as well as our text elements (i.e. ```<p>```, ```<h1>```/```<h2>```/other headers, <ul>```/```<li>```). Block elements will always start and end on their own line. For example, if you were to write the following (very invalid, do not do this) HTML:

	<p>This is a paragraph with an <h2>embedded header</h2> and then some text after.</p> with more text after the paragraph ends.

it would render as 
<div style="background: #cccccc">
<p>This is a paragraph with an <h2>embedded header</h2> and then some text after.</p> with more text after the paragraph ends.
</div>

Other elements that are within text are called ```inline``` elements and include elements used to style text (i.e. ```<span>```, ```<a>```, ```<strong>```, ```<em>```, etc.). Inline elements don't force text to a new line, and format the text inline with other elements. [Here's a full list](https://www.w3schools.com/html/html_blocks.asp) of inline and block elements.

While block elements can be styled to a specific height and width with CSS, inline elements cannot. An inline element is exactly the height and width of the items it contains. We will discuss borders and margins later - while block elements can have margins and borders on all four sides, inline elements can only have margins and borders on the left and right side, since the height is set by the elements it contains. A third category, called ```inline-block``` can be used to set the height and width of inline elements. No elements are ```inline-block``` by default.

While each HTML element has a default behavor of ```block``` or ```inline```, these can be overriden within CSS using the ```display``` attribute. For example, if you wanted to have a special type of link that was always on a line by itself, you could add the following to your CSS:

	.major-link{
		display: block;
		font-size: 2em;
	}

And then the following HTML:

	<p>This is an example of an inline link to the <a class="major-link" href="http://www.google.com">Googles</a>, which is kind of something you might use one day.</p>

would produce:

<div style="background: #cccccc">
<p>This is an example of an inline link to the <a style="display: block; font-size: 2em;" href="http://www.google.com">Googles</a>, which is kind of something you might use one day.</p>
</div>

<a href="https://www.samanthaming.com/pictorials/css-inline-vs-inlineblock-vs-block/">Read more about block, inline, and inline block</a>

## Padding, Borders, Margins

Remember from above that all elements are basically rectangles. Within the rectangle, there are three ways to add spacing around an element - padding, borders, and margins. A border is the same as a border in a spreadsheet or a table in Excel or Word - a line (visible or invisible) that goes around the rectangle. You can style the line to be any thickness or color that you want, and there are a few other options for it as well. Padding is the white space between the element (i.e. your text) and the border whereas margins are the white space around the element on the outside of the border. Collectively, these are known as the **CSS Box Model** and can be used to style and place content on a site, and to add spacing around elements on your site.

![CSS Box Model](https://upload.wikimedia.org/wikipedia/commons/7/7a/Boxmodell-detail.png)

Margins, borders, and padding can be applied to any of the four sides of the rectangle, and are not all required (i.e. you can have a box with a margin and no padding, or vice-versa). The primary difference between padding and margin is the side of the border that they appear on, and that elements like background colors apply in the padding, but not in the margins. The total width and height of a rectangle is the element size, plus the padding, plus the border size, plus the margin. In your browser developer tools, you can preview the size of the entire box.

Padding and margins can be applied using the elements ```padding-top```, ```padding-right```, ```padding-bottom```, and ```padding-bottom``` (or margin, respectively). There's also a shortcut where you can use an element as follows in your css:
	
	padding: top right bottom left;

padding is specified in pixels or percentages, but pixels are typically used:

	padding: 10px 5px 10px 5px;

You can use three values:

	padding: top right/left bottom;

or two:

	padding: top/bottom right/left;

The same syntax will apply for margins, substitute the word "margin" for the word "padding". Padding values are always positive. Margin values can be negative to encroach on another elements space, but this can be unpredictable and is best avoided. 

Borders use a similar syntax, wherein a border can be specified differently on all four sides of the box, or for the entire box. The ```border``` attribute takes three arguments:

	border: size style color;

size is a value in pixels. Style is the type of border to be used [(values are solid, dotted, dashed, double, groove, ridge, inset, outset, none, hidden)](https://www.w3schools.com/css/css_border.asp). Color is a CSS color or a color code.

A second attribute ```border-radius``` is optional and takes an argument in pixels, and can round the border. The larger the radius, the more round the border is.

You can use padding and margins for lots of different applications. An easy one is to turn links into buttons. For example, using the following CSS, I can build this ugly button that is overdramatized for demo purposes:

	.link-button{
	  display: inline-block;
	  color: white;
	  background: red;
	  padding: 25px 50px;
	  border: 10px solid darkred;
	  border-radius: 10px;
	}

and the HTML

	<a href="http://www.google.com" class="link-button">Google!</a>

would yield:

<a href="http://www.google.com"  style="  display: inline-block; color: white; background: red; padding: 25px 50px; border: 10px solid darkred; border-radius: 10px;">Google!</a>

### Boxes in Boxes

One of the biggest applications of margins, padding, and borders is a concept called "boxes in boxes". This is styling when one HTML box is placed inside another. Typically, this is also (but not necessarily) paired with the ```width``` and ```height``` attributes to specify the width and height of the boxes, either as a set number of pixels, or percentage of the parent elements. You can use ```min-width```/```min-height``` or ```max-width```/```max-height``` as well to set the "not less than" and "not to exceed" amounts.

Operationally, take a look at this example. Notice that the ```.box``` class is styled as ```display: inline-block```. This is because a ```block``` element would push the other divs to a new line, and an ```inline``` element would not allow the styling of top and bottom margins/padding. Also, notice the margins on the left and right add 25px on each side, meaning there are 50px between each box (i.e. a 25px right margin on box 1 and a 25px left margin on box 2). 

HTML

	<section class="main-demo-section">
	  <div class="box" id="box1">
		Box 1
	  </div>
	  <div class="box" id="box2">
		Box 2
	  </div>
	  <div class="box" id="box3">
		Box 3
	  </div>
	  <div class="box" id="box4">
		Box 4
	  </div>
	</section>

CSS:

	.main-demo-section{
	  height: auto;
	  background-color: blue;
	  color: white;
	  height: 300px;
	}
	
	.box{
	  margin: 25px;
	  padding: 25px;
	  display: inline-block;
	  text-align: center;
	  font-weight: bolder;
	  font-size: 2em;
	}
	
	#box1{
	  background-color: red;
	  height: 100px;
	}
	
	#box2{
	  background-color: green;
	  height: 50%;
	}
	
	#box3{
	  background-color: purple;
	  min-height: 60px;
	  min-width: 15%;
	}
	
	#box4{
	  background-color: orange;
	  width: 15%;
	}

Result:

<style>
.main-demo-section{
	  height: auto;
	  background-color: blue;
	  color: white;
	  height: 300px;
	}
	
	.box{
	  margin: 25px;
	  padding: 25px;
	  display: inline-block;
	  text-align: center;
	  font-weight: bolder;
	  font-size: 2em;
	}
	
	#box1{
	  background-color: red;
	  height: 100px;
	}
	
	#box2{
	  background-color: green;
	  height: 50%;
	}
	
	#box3{
	  background-color: purple;
	  min-height: 60px;
	  min-width: 15%;
	}
	
	#box4{
	  background-color: orange;
	  width: 25%;
	}
</style>
<section class="main-demo-section">
  <div class="box" id="box1">
	Box 1
  </div>
  <div class="box" id="box2">
	Box 2
  </div>
  <div class="box" id="box3">
	Box 3
  </div>
  <div class="box" id="box4">
	Box 4
  </div>
</section>


 
