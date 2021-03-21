---
layout: page
title: "JavaScript Libraries and APIs"
course: "webdev"
unit: 9
---

While jQuery is one example of a library, there are many others - many that implement specific functions. Combined with libraries that help you implement functions in JavaScript, **Application Programmer Interfaces (APIs)** in JavaScript and other languages can help you use JavaScript to make complex tasks easier. There are literally [hundreds](https://www.freecodecamp.org/news/10-javascript-libraries-you-should-try/) and [hundreds](https://getflywheel.com/layout/best-javascript-libraries-frameworks-2020/) of [JavaScript Libraries](https://en.wikipedia.org/wiki/List_of_JavaScript_libraries) and and APIs. Many APIs are *RESTFul* which we will discuss in the next unit, but basically means that they make web requests back and forth. 

When using a library, you want to look for the _CDN_ URL, which you can add to your HTML file directly like we did with jQuery. This will download and include the library from the CDN server. Every library has their own functions and syntax - I wish there was a "recipe", but there isn't. You'll need to read the documentation for each library to understand what they do and how they work, but know that you can use regular JavaScript along with the specialized functions. Below are some examples of JavaScript libraries, mixed with regular JavaScript code.

## [Bootstrap Datepicker](https://github.com/uxsolutions/bootstrap-datepicker)
This example uses the Bootstrap Datepicker library to create a form element with a built in calendar. Note that the [CDN site](https://github.com/uxsolutions/bootstrap-datepicker) is complicated, generally you'll only need the first few items in the list to get started. Once the site is set up, the [documentation](https://bootstrap-datepicker.readthedocs.io/en/stable/) can help you get set up and running quickly. 

<p class="codepen" data-height="334" data-theme-id="dark" data-default-tab="html,result" data-user="mjsamberg" data-slug-hash="bGgbbOy" style="height: 334px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Unit 9 - Bootstrap Date Picker">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/bGgbbOy">
  Unit 9 - Bootstrap Date Picker</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

Note that CodePen obscures the JS and CSS includes. The code to include this is:

With your CSS files:

	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/bootstrap-datepicker/1.9.0/css/bootstrap-datepicker.min.css" integrity="sha512-mSYUmp1HYZDFaVKK//63EcZq4iFWFjxSL+Z3T/aCt4IO9Cejm03q3NKKYN6pFQzY0SBOr8h+eCIAZHPXcpZaNw==" crossorigin="anonymous" />
	
After your jQuery include:
	
	<script src="https://cdnjs.cloudflare.com/ajax/libs/bootstrap-datepicker/1.9.0/js/bootstrap-datepicker.min.js" integrity="sha512-T/tUfKSV1bihCnd+MxKD0Hm1uBBroVYBOYSk1knyvQ9VyZJpc/ALb4P0r6ubwVPSGB2GvjeoMAJJImBG12TiaQ==" crossorigin="anonymous"></script>
	

## [MathJax](http://docs.mathjax.org/en/latest/web/start.html)
MathJax is a JavaScript library that converts LaTEX and math printing to HTML. This is more accessible and easier than the traditional approach of using images. LaTeX code is encapsulated in ```\( ... \)``` for the same line and ``` $$ ... $$``` for the math to appear on its own line. [Online LaTEX Editors](http://www.sciweavers.org/free-online-latex-equation-editor) can help you generate the LaTeX code to be included. 

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="html,result" data-user="mjsamberg" data-slug-hash="xxgKKoX" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="xxgKKoX">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/xxgKKoX">
  xxgKKoX</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

It's included using:

	<script type="text/javascript" id="MathJax-script" async
	  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
	</script>
	
## [ChartJS](https://www.chartjs.org)
ChartJS is a really neat library that allows you to make charts from JavaScript objects. 

It's included with 
	
	<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.4/Chart.bundle.min.js" integrity="sha512-SuxO9djzjML6b9w9/I07IWnLnQhgyYVSpHZx0JV97kGBfTIsUYlWflyuW4ypnvhBrslz1yJ3R+S14fdCWmSmSA==" crossorigin="anonymous"></script>
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.4/Chart.min.css" integrity="sha512-/zs32ZEJh+/EO2N1b0PEdoA10JkdC3zJ8L5FTiQu82LR9S/rOQNfQN7U59U9BC12swNeRAz3HSzIL2vpp4fv3w==" crossorigin="anonymous" />

And you can create charts using JavaScript objects:
<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="js,result" data-user="mjsamberg" data-slug-hash="bGgbGeN" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Unit 9 - Chart.js">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/bGgbGeN">
  Unit 9 - Chart.js</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

While these are hard-coded, you can take user input for this as well. While we can't store input yet, we will be able to by the end of the next unit. But here's an example that works similarly, without storage.

<p class="codepen" data-height="500" data-theme-id="dark" data-default-tab="result" data-user="mjsamberg" data-slug-hash="poRzoeN" style="height: 500px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Unit 9 - Chart.js Dynamic Example">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/poRzoeN">
  Unit 9 - Chart.js Dynamic Example</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>





