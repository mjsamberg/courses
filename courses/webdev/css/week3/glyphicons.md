---
layout: page
title: "Glyphicons"
course: "webdev"
unit: 6
---
There are many icons in use across web pages as both navigational aids and links to an organization's presence in common brands (i.e. Twitter, Facebook, GitHub, etc.). These icons can be cumbersome to use as images, since you would need an image at various sizes, and in every color combination you would need across your site. You could resize the image, but depending on the source image, resizing can make an image blurry or otherwise unusable.

To solve these issues, a new type of CSS framework was created: Glyphicons. Glyphicons are fonts where each character is an icon image. By using a font instead of an image, you can style glyphicons using your regular CSS font commands and they can be scaled to any size (think: Wingdings). Most glyphicons generally work the same - the ```<i>``` tag is repurposed for the icons (since it's not really used much anymore), and use CSS classes to replace the tag with the glyphicon. You'll see more in the two examples below. The two primary glyphicon frameworks we'll discuss are Bootstrap Icons and Font Awesome.

## Bootstrap Icons
Bootstrap icons are brought to you by the same people who create the Bootstrap framework. Bootstrap icons are added to your doc by adding the following to your HTML file right above where you include Bootstrap:

	<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.8.1/font/bootstrap-icons.css">

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.8.1/font/bootstrap-icons.css">

From there, you can browser the [Bootstrap Icons Website](https://icons.getbootstrap.com) to find the icon you want to use, and the HTML for including it directly is on the page (use the _Icon Font_ option). 

For example, if I want the "Person" icon, I would use the following code:

	<i class="bi bi-person-fill"></i>

The result would produce the following icon:

<i class="bi bi-person-fill"></i>

I can add additional classes to this tag in order to change the size or the color, i.e.:

	<i class="bi bi-person-fill icon-vvlarge icon-blue"></i>

with the following CSS:

	.icon-vvlarge{
		font-size: 24px;
	}
	
	.icon-blue{
		font-color: blue;
	}
	
which would yield:
<style>
.icon-vvlarge{
	font-size: 72px;
}

.icon-blue{
	color: blue;
}
</style>
<i class="bi bi-person-fill icon-vvlarge icon-blue"></i>

You can also use the glyphicons inside other containers. For example, a right arrow after a link:

	<a href="http://www.ncsu.edu">NC State University <i class="bi bi-arrow-right-short"></i></a>

yields:

<a href="http://www.ncsu.edu">NC State University <i class="bi bi-arrow-right-short"></i></a>

## Font Awesome
[Font Awesome](https://fontawesome.com) is a much larger library of icons with a free tier and multiple paid tiers. The free tier library is very large and Font Awesome is much more widely used than Bootstrap Icons. You can create a free Font Awesome account to gain access to the library and to include the icons in your site. 