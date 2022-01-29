---
layout: page
title: "The Anatomy of an HTML Document"
course: "webdev"
unit: 2
---

## Starter Template
All HTML files will use some variation of the following starter template. While you will likely add components to it over time, these components are all still there:

	<!DOCTYPE html>
	<html lang="en">
		<head>
			<title>Welcome to my Virtual Terrarium</title>
			<meta charset="utf-8" />
			<meta http-equiv="X-UA-Compatible" content="IE=edge" />
			<meta name="viewport" content="width=device-width, initial-scale=1" />
			<meta name="description" content="A brief description of this page and what's on it (it will be displayed in Google). Should be about 240 characters." />
			<meta name="author" content="Your name or company name here" />
		</head>
		<body>
			Main content goes here.
		</body>
	</html>

The first line, the ```DOCTYPE``` tag informs the browser that the page it has received is an HTML page and should be rendered as such. The ```<html>``` tag is the container tag for the entire page in the DOM. Only the content between the ```<html>``` tag will be interpreted and rendered by the browser.

The ```<head>``` tag is not displayed to in the browser, but contains instructions to help the browser render the page including "metadata" (data about the web page). The ```<title>``` tag contains the title that is displayed on the title bar and in the tab headers on your browser window.

The ```<meta>``` tag contains metadata that a browser can interpret to help render the page or extract data from the page (for example, there are a whole set of meta tags called [OpenGraph](https://developers.facebook.com/docs/sharing/webmasters/) that will render how a page displays on a Facebook share sheet). The three in the starter template are all required. The ```charset``` meta tag defines the character set to be used. The UTF-8 character set includes the standard English characters, most of the symbols used in modern typing, and emoji. You may use other character sets other languages that do not use the Latin character set (i.e. Chinese, Hebrew, Arabic, Japanese, Russian). The ```X-UA-Compatible``` meta tag is a legacy Internet Explorer holdover and is required in HTML 5. It just needs to be included. The [```viewport``` tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag) is generally not changed from the starter template. It evolved in HTML as devices of varying screen geometries became more prevalent (portrait, landscape, small, large). It defines the scaling that should be used when a page is first displayed so that it isn't intentionally cut off on the sides. The tag as provided means that the page should be displayed as scaled such that the entire width of the page appears in the window and that the initial zoom level should be 100%.

The ```body``` tag is where the HTML content that is displayed in the browser lives. All of the text and tags that are displayed on a webpage should be placed between the body tags.

## Semantic Styling
_Semantic styling_ means that elements in HTML are defined by ***what they are*** versus how they should appear. We will be using CSS to define the appearance of the elements, and most browsers have default styles that they apply to different elements. In early versions of HTML, elements were not defined semantically. In the early days of HTML, if you wanted to emphasize text by making it _italic_, you would use the ```<i>``` tag. However, in semantic HTML (required by HTML 5), you would use the ```<em>``` tag to define text as emphasized text. By default, it would be rendered in italics, but that could be changed by CSS. In addition to allowing elements to be styled differently, semantic tags allow browsers to interpret content for a variety of other purposes - the "reader mode" in most browsers has the capability of extracting content in an ```<article>``` tag, allowing for distraction-free viewing. The semantic tags can also be used by assistive devices to help people with disabilities interpret the meaning behind your content.

### Content Sections
Content section elements define the different sections on the page. For example, in a blog post, you could surround the blog article with the ```<article>``` tag, and navigate to the different sections of your blog with the ```<nav>``` tag. Review the [full list of content section tags](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#content_sectioning). The finished product would look like this:
	<article>
		My text goes here.
	</article>

Sometimes, the list of content section tags doesn't accurately define a section. In that case, the ```<div>``` tag is used to define a section where a specific semantic tag is not appropriate. ``<div>``` which basically means "none of the above, but we're going to group this bunch of content together for formatting purposes".

### Text Content
Within the page [text sections](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#text_content) are used to identify blocks of text. The most common ones you'll use are ```<p>``` which are paragraphs and ```<span>``` which is inline text. ```<p>``` will add line breaks above and below the paragraph, whereas ```<span>``` continues formatting inline.

So for a paragraph, you would simply put the tag in between the ```<p>``` tag:
	<p>My paragraph goes here.</p>
	
Headings are also important ways to break up a page. There are six levels of headings in HTML, represented with ```<h1>``` - ```<h6>```. Headers should be "nested" such that level 2 headers exist under level 1 headers and level 3 headers exist under level 2 headers.

	<h1>My level 1 header</h1>
	
yields:

<h1>My Level 1 Header</h1>

Within this list of tags are lists. Lists use two elements: the ```<ol>``` tag for numbered lists and the ```<ul>``` tag for bulleted (unordered) lists. Within those tags you would use ```<li>``` for individual items like so:

	<ul>
		<li>List item 1</li>
		<li>List item 2</li>
	</ul>

This would produce the following:
<ul>
<li>List item 1</li>
<li>List item 2</li>
</ul>

### Text Formatting
Within text blocks, inline text elements allow you to format text in a certain way. ```<strong>```, for example, creates strong (bold) text and ```<em>``` creates emphasized (italic) text. The readings below will dig deeper into these.

### Other Elements
There are other elements that are in HTML as well. We'll explore a lot of these later in the course, but the two to know at this point are ```<br/>``` which is a line break (like pressing the return key on the keyboard) and ```<hr/>``` which stands for "horizontal rule" and adds a line across the screen (see below). The difference between ```<br/>``` and ```<p>``` is that ```<br/>``` is a line break that doesn't start a new paragraph. Think about a poem. In order to write a poem like:
<p><em>An old silent pond...<br/>
A frog jumps into the pond,<br/>
splash! Silence again.</em></p>

you would use HTML as follows:
	<p>
		<em>An old silent pond...<br/>
		A frog jumps into the pond,<br/>
		splash! Silence again.</em>
	</p>

Because ```<br/>``` doesn't contain any elements, we combine the opening and closing tag into a single tag by putting the slash mark at the end. Same with the ```<hr/>``` tag.

<hr>

### Character Entities
So we know that the &lt; and &gt; symbols are used to open and close HTML tags. But what happens if you want to actually use the &lt; symbol in your text, say for a math equation. [HTML character entities](https://developer.mozilla.org/en-US/docs/Glossary/Entity) are used to render specific characters. For example, if you wanted the &lt; symbol, instead of typing it on your keyboard, you would insert ```&lt;``` which the browser would interpret as you wanting to display the less-than symbol. The other ones that are commonly used are ```&gt;``` for the greater-than symbol (&gt;); ```&amp;``` for the ampersand (&amp;) and ```&quot;``` for quotation marks ("). While there are many others, the use of these four are required for code that will always render properly in the browser.

## Read and Do
Read the following activities from Mozilla and complete the embedded activities:
* [HTML Text Fundamentals](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals)
* [Advanced Text Formatting](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting)

Next, review this [simple example](https://codepen.io/mjsamberg/pen/YzGRWLV?editors=1000). While it's unformatted (again, we'll get to that) you can see how the different elements work on the page.
