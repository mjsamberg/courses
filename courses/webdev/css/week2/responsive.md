---
layout: page
title: "Responsive CSS"
course: "webdev"
unit: 5
---

Responsive design in CSS allows your document to change to accommodate different interfaces. For example, we can hide navigational elements on a page for printing, or change the size of the elements on a page so it will look better on mobile devices, or we can add text that will only be read to screen readers.

Responsive design in CSS occurs primarily with new tools such as Flexbox, but also, using a CSS element called a _media query_. Media queries, by convention, are placed at the end of your CSS file and are used to override the default settings that are elsewhere in your CSS (remember that your CSS is processed linearly, so set the "default" appearance in your CSS, and your media queries at the end will change it based on the query conditions). Web browsers automatically apply the base CSS, and then apply the CSS in the media query when it applies. 

Media queries use the syntax

	@media media-type{
		//Media CSS goes here - Media CSS is the same as regular CSS.
	}

Basic acceptable values for ```media-type``` are ```screen``` (for all screens), ```print```, and ```speech``` (for screen readers). The ```display: none;``` attribute is used to hide elements. For example, if I wanted to hide my ```<nav>``` element when printing a document, I would use the following CSS:

	@media print{
		nav{
			display: none;
		}
	}

### Breakpoints
While there are [many more attributes to extend media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries), the most common (aside from ```screen```, ```print```, and ```speech```) are the ```max-width``` and ```min-width``` attributes. Since most mobile devices are different screen widths than desktops, the width attribute is used to create a "breakpoint" where the page will display differently based on the window width, creating a "mobile-friendly" version. You can emulate this on your computer by shrinking the width of your browser window and noticing how your page reflows. Dev tools in the browser also has a "Responsive Design Mode" which allows you to see the page on different browsers. The typically-used breakpoints are as follows. Keep in mind that not every project will use every breakpoint.

	// Small devices (landscape phones, up to 768px)
	@media (max-width: 767px) { ... }
	
	// Medium devices (tablets, 768px and up)
	@media (min-width: 768px) { ... }
	
	// Large devices (desktops, 992px and up)
	@media (min-width: 992px) { ... }
	
	// X-Large devices (large desktops, 1200px and up)
	@media (min-width: 1200px) { ... }

So for example, let's look a the _lorem ipsum_ callout box on the previous page. A callout box works well on a desktop, but on a mobile device, it may impact readability. So on mobile devices and tablets, I want the callout box to be the width of the page instead of a callout box. Because I want tablets to be included, I'll use ```@media (max-width: 991px)``` as my media query and because I don't want ```float:right;``` on mobile, I'll use ```float: clear``` to unset that value. I'm also going to change the color of the background and the text, for illustration purposes and change the margin so that the callout is centered on the screen. Review the example below and change the width of the window to see how the page reacts to the changes:
<p class="codepen" data-height="400" data-theme-id="light" data-default-tab="result" data-user="mjsamberg" data-slug-hash="LYbxBON" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="ECI519 - Unit 5 - Responsive">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/LYbxBON">
  ECI519 - Unit 5 - Responsive</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

### Dark Mode
Many modern phones and browsers offer a "dark mode". In CSS, the browser can automatically detect and apply a different stylesheet for dark mode using media queries. For example:

	@media (prefers-color-scheme: dark){
		html{
			background-color: black;
			color: white;
		}
	}

<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>


