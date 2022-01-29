---
layout: page
title: "Using CSS to Format Text"
course: "webdev"
unit: 4
---
## Colors in HTML and CSS
When colors are required in CSS, you can use the names of about [100 different colors](https://www.rapidtables.com/web/css/css-color.html) to specify the colors of texts, backgrounds, and borders. But HTML is capable of displaying 16,777,216 different colors using hexadecimal color codes_. [Hexidecimal is a base-16 number system](https://simple.wikipedia.org/wiki/Hexadecimal) that is often used as a shorthand for binary code (one hexadecimal character replaces up to four places of binary code). Hexadecimal numbers go from 0-9 and since we need more characters, we also use the letters A-F to represent the base-10 numbers 10-16 (understanding this is beyond the scope of the course, but please feel free to dig in). 

Anyway, HTML color codes are made up of six hexadecimal numbers - the first two representing the amount of red, the second being the amount of green, and the third being the amount of blue. ```00``` represents none of the color while ```FF``` means all of the color. We use a pound sign in the beginning to denote the color codes. For example, no color (black) would be represented as ```#000000``` while all colors at full intensity (white) is ```#FFFFFF```. Pure red with no other colors is ```#FF0000```, and pure green and blue are ```#00FF00``` and ```#0000FF``` respectively. By mixing different amounts of red, green, and blue, you can create any combination of the 16,777,216 colors and represent them using the hexadecimal codes. This is not too different from the way paint colors are made. CSS can also represent these values using other methods, but this is the primary one we will be using now.

Using an [Color Picker tool](https://htmlcolorcodes.com/color-picker/) will allow you to pick different colors for your website, and apps like [Coolors](https://coolors.co) can allow you to identify color combinations that are complimentary in web design. 

## Fonts
### Font Sizes
Fonts in CSS can be specified using five main types of values (though there are [lots of others](https://www.w3schools.com/cssref/css_units.asp) less often used. The font size can be specified in absolute units ```px``` or the number of pixels long a character is or ```pt``` which is points like in a word processor (pixels and points are very similar units). 

It is recommended that you set a default font size for your entire page by assigning a font size to the ```html``` element as follows:

	html{
		font-size: 12px;
	}

This will default all elements to 12px. Doing this enables you to open up two _relative_ font sizes. In our example, with a 12px default, the ```rem``` attribute value be used to specify the font size relative to the default element. For example, if we have in our stylesheet:

	h1{
		font-size: 2rem;
	}

Our root element is 12px, and therefore our ```h1``` element would be 24px. If I wanted to make all of the fonts on the page larger, I would simply have to change the root font size and everything would follow. Another type of relative font size is the ```em``` parameter which is more confusing because it means that it relative to the parent. In our same stylesheet, consider the following HTML:

	<section class="lunch-menu">
		<h2>Weekly Lunch Menu</h2>
		<p>Just a plate of vegetables</p>
	</section>

and the following CSS:

	.lunch-menu{
		font-size: 1.25rem;
	}
	
	.lunch-menu h1{
		font-size: 1.5em;
	}

In this case, the entire ```.lunch-menu``` section would be 1.25 the root element (12px), or 15px. The ```.lunch-menu h1``` element would be sized as 1.5 times the parent element (1.5 * 15 = 22.5px). 

The fourth type is ```vw``` which is the percentage of the width of the window the font takes up. This is rarely used.

### Inline Formatting
Sometimes, you want to highlight parts of text without styling an entire container. You can apply CSS to inline formatting containers as well. For example, if you have vocabulary words on a webpage, i.e. 

	The quick brown fox <strong class="vocab">jumped</strong> over the lazy dog.

you could style the ```.vocab``` class:

	.vocab{
		font-weight: bold;
		color: red;
	}

If none of the semantic inline tags are appropriate for defining an item, ```<span>``` is the generic class.

	Order your CD now for only <span class="price">$9.95</span>.

And you could style with:

	.price{
		color: green;
	}

### Text Formatting in CSS
**Read the Following Items**
* [Styling Fonts with CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)
* [Formatting Text with CSS](https://www.tutorialrepublic.com/css-tutorial/css-text.php)
* [Styling Links with CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Styling_links)

### Adding Additional Fonts
While the list of web-safe fonts is very small, it is possible to add fonts in CSS using online font foundries. One popular one is [Google Fonts](https://fonts.google.com). This [video has instructions for using Google Fonts](https://youtu.be/lFLB9xo5Da8), though note that the layout has changed slightly since the video was produced.

## Formatting Other Elements
Please review the following links for other CSS elements that can be used:
* [CSS Lists](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Styling_lists)
* [CSS Tables](https://www.tutorialrepublic.com/css-tutorial/css-tables.php)

### Images
In the last unit, I had an example of an image

	<img src="https://brand.ncsu.edu/assets/logos/ncstate-type-2x2-red-max.png" alt="NC State University Logo" style="width: 25%; height: auto;" />

As you're now aware, the style part of this image tag is CSS. You can do inline styling like this, or you can use CSS classes:

	<img src="https://brand.ncsu.edu/assets/logos/ncstate-type-2x2-red-max.png" alt="NC State University Logo" class="logo" />

and move the CSS into your stylesheet:

	.logo{
		width: 25%;
		height: auto;
	}

See [this article on W3Schools](https://www.w3schools.com/css/css3_images.asp) for other image styling.

## Full List
CSS Tricks.com maintains a [full list of usable CSS attributes with documentation](https://css-tricks.com/almanac/properties/)

