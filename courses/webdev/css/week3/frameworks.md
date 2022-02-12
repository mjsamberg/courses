---
layout: page
title: "Bootstrap and CSS Frameworks"
course: "webdev"
unit: 6
---
As you may have noticed by now, creating CSS code for a large, comprehensive website would be an incredibly time-consuming challenge. Designing each element by hand while ensuring consistency and functionality across multiple browsers and screen sizes is an incredibly time-consuming task. CSS Frameworks take a lot of the work out of this process. Most CSS frameworks are hundreds of thousands of lines of pre-written CSS Code, that is already set up and ready for you to use. Most frameworks have classes pre-built for responsive design, for different types of semantic elements, and for different types of displays. Because of the inheritance model in CSS, you can always add and override the classes used in the framework in order to produce a custom website.

Think about CSS frameworks like a cake mix - most of the ingredients are there, but you can add eggs (your content), but you can also add extras like candies or chocolate chips (your custom CSS).

CSS Frameworks also allow for consistently. Large organizations, including NC State, develop their own CSS frameworks that typically extend other frameworks. By including the framework in a site, it will instantly appear consistent with other sites. 

Frameworks can be modified, compiled, and included as a part of your project (we won't be covering this process in this course, [but here are instructions for the daring](https://getbootstrap.com/docs/5.0/getting-started/build-tools/)). Typically, frameworks are included through a **CDN** (Content Distribution Network) which is a very fast web server that serves CSS and JavaScript frameworks that people use in their projects. By using a CDN, you can get bug fixes and new features in real time, and you do not have to host the framework yourself. 

## Bootstrap
For this course, we will be diving deeply into one framework, Bootstrap. Bootstrap originally started as the framework for use in Twitter's internal tools. It eventually was spun out into a standalone open-source project and is one of the most heavily used open source projects on the Internet. Bootstrap has a variety of semantic classes that allow you do create very rich webpages with minimal amounts of code. Check out a [quick demo page](https://media.fi.ncsu.edu/bootstrap/template.html) I use to demonstrate some of the features of Bootstrap. This page is not exhaustive, and each of the items on this page can be accomplished using the framework out-of-the-box with only a few lines of code.

### Adding Bootstrap to your Project

Bootstrap has two components that need to be added - the CSS and the JavaScript. The CSS line of code should be added, exactly as below, **right before you include your site's CSS** in the ```<head>``` tag. Simply cut and paste the following code:

	<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">

The JavaScript needs to be included immediately **before** your closing ```</body>``` tag at the bottom of your document. These JavaScript libraries allow for some of the interactivity in the site (pop-up windows, collapsable panels, etc.). Simply cut and paste the following code:

	<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
	
### Containers
Last week we discussed adding margins and spacing and the CSS box model, specifically as it pertains to keeping elements from going all the way to the edge of the screen. Bootstrap has some tools for page and block-level boxes, called *containers*. [Read more about Bootstrap containers](https://getbootstrap.com/docs/5.0/layout/containers/).
	
### The Grid System

The hallmark feature of Bootstrap is the responsive grid system. In the previous unit, we had to write a significant amount of CSS in order to create three responsive boxes in a row on a page. In bootstrap, we can accomplish this with one line of code, using the grid system. Bootstrap imagines that the page is divided into 12 columns, each being 1/12th of the screen. Using CSS classes, you can tell Bootstrap how big each column should be at each breakpoint. Bootstrap uses six breakpoints (```xs``` (extra-small, for very small screens, ```sm``` (small, for most mobile phone screens), ```md``` (medium, for most laptops), ```lg``` (large, for large external monitors), ```xl``` (extra-large, for very large displays)). In the grid system, these are interpreted to mean _and up_, meaning that if you only specify ```xs```, it is interpreted to mean ```xs``` and everything larger. If you specify ```xs``` and ```md``` (common practice), it typically means ```xs``` and up (to ```md```) and then ```md``` and up through ```xl```. That keeps you from having to specify each breakpoint.

Let's look at this in action. Suppose I want a row of boxes and I want four boxes on my screen, unless I'm on mobile (in which case, I want each box to be its own line). You would start by specifying a row, and then a column with a value of the number of cells. So, if each cell is 1/12th and I want four boxes on a line, each box would be 3 cells wide. Therefore, all I have to do in my HTML is this:

	<div class="row">
		<div class="col-xs-12 col-md-3">
			Box 1
		</div>
		<div class="col-xs-12 col-md-3">
			Box 2
		</div>
		<div class="col-xs-12 col-md-3">
			Box 3
		</div>
		<div class="col-xs-12 col-md-3">
			Box 4
		</div>
	</div>
	
This would yield the following:

<div class="row">
<div class="col-xs-12 col-md-3">
	Box 1
</div>
<div class="col-xs-12 col-md-3">
	Box 2
</div>
<div class="col-xs-12 col-md-3">
	Box 3
</div>
<div class="col-xs-12 col-md-3">
	Box 4
</div>
</div>

That's it! There's nothing to do in the CSS. The ```row``` class defines a new row,  the ```col-xs-12``` class indicates that the box should be 12 cells wide at the ```xs``` and above breakpoint and then 3 units wide at the ```md``` and above breakpoint. 

You can always add custom CSS if you want, by adding an additional class anywhere. For example, if I wanted the row to be blue, I could add a ```blue``` class to my row and define it in CSS:

	<div class="row blue">
		<div class="col-xs-12 col-md-3">
			Box 1
		</div>
		<div class="col-xs-12 col-md-3">
			Box 2
		</div>
		<div class="col-xs-12 col-md-3">
			Box 3
		</div>
		<div class="col-xs-12 col-md-3">
			Box 4
		</div>
	</div>

and add the following to my CSS:

	.blue{
		background-color: blue; 
		color: white;
	}

<div class="row" style="background-color: blue; color: white;">
<div class="col-xs-12 col-md-3">
	Box 1
</div>
<div class="col-xs-12 col-md-3">
	Box 2
</div>
<div class="col-xs-12 col-md-3">
	Box 3
</div>
<div class="col-xs-12 col-md-3">
	Box 4
</div>
</div>

Remember, the grid is only there for options if you want to use a divided screen. If you want full-width elements, there is no need to use the grid. There are many more options for the grid system, including offsets, vertical alignment, etc. [**Review the Bootstrap Documentation for the Grid System**](https://getbootstrap.com/docs/5.0/layout/grid/)

### Display Elements
Bootstrap has a number of display elements that make things easier. For example, to center horizontally in pure CSS, you needed to add the following CSS to your code:

	.center{
		margin: auto;
		display: block;
	}

Bootstrap has already done the work for you and you can simply use the pre-existing ```.mx-auto``` class. You can also do things like ```.mb-5``` to include a large margin. ***In fact, everything we discussed in the unit last week can be replaced with pre-existing Bootstrap classes (sorry not sorry).**

[**Review everything in the _Utilities_ section of the Bootstrap documentation**](https://getbootstrap.com/docs/5.0/layout/utilities/)

### Semantic Elements
In addition to display elements, Bootstrap has a number of pre-made semantic elements that can be used to add specific types of content to your webpage including buttons, alerts, special types of lists and tables, etc. The most useful is the _card_ which looks like the following:
	
	<div class="card">
	  <h5 class="card-header">Featured</h5>
	  <div class="card-body">
		<h5 class="card-title">Special title treatment</h5>
		<p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
		<a href="#" class="btn btn-primary">Go somewhere</a>
	  </div>
	</div>

and displays as 

<div class="card">
  <h5 class="card-header">Featured</h5>
  <div class="card-body">
	<h5 class="card-title">Special title treatment</h5>
	<p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
	<a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>

[**Review everything in the _Content_ and _Components_ sections of the Bootstrap documentation**](https://getbootstrap.com/docs/5.0/components/)

### Extending Bootstrap
You can extend Bootstrap in a number of ways. You can change your fonts same as before. You can also add CSS to Bootstrap classes. For example, if you want all ```.col-md-6``` boxes to be gray, you can add the following to your CSS:

	.col-md-6{
		background-color: gray;
	}

Because of CSS's inheritance model, the styling from both the Bootstrap stylesheet and from your stylesheet will be applied. [Bootstrap.build](https://bootstrap.build) is a free site that will let you bake-in some changes to CSS easily, such as new color schemes and would replace the Bootstrap ```<link>``` from above.

#### Colors
Bootstrap contains _variables_ that you can use in your CSS instead of using HTML color codes for certain colors. This will ensure that the colors of your text will always match the colors used in Bootstrap. You can use these as follows. In your CSS, instead of using a reserved color code or hex code, use the following:

	.color-example{
		color: var(--blue);
	}

Acceptable values inside of ```var``` are ```--blue```, ```--indigo```, ```--purple```, ```--pink```, ```--red```, ```--orange```, ```--yellow```, ```--green```, ```--teal```, ```--cyan```, ```--white```, ```--gray```, ```--gray-dark```.

There are also colors for ```--primary``` (your site's primary color), ```--secondary``` (your site's secondary color), as well as for the different error states that you can see throughout bootstrap's code: ```--success```, ```--info```, ```--warning```, ```--danger```.

## Other Frameworks
Bootstrap is not the only framework available. [Tailwind](https://tailwindcss.com) is a new one that's gaining a lot of popularity. It's much more popular than Bootstrap, but is much more complicated to use.