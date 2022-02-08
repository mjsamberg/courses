---
layout: page
title: "Positioning Elements with CSS"
course: "webdev"
unit: 5
---

Using CSS to position elements on a page is one of the most complicated, but also the most powerful, elements of CSS. The frameworks we will discuss next week make much of this work easier. However, the ability to position elements on a page gives us much of the interactivity and richness that we take for granted on the modern Web. On this page, we will review a few tools that can be used to position elements using CSS. Specifically pay attention to floats and to Flexbox, those are two elements that you will likely be using often. Most of the information on this page  links out to [CSS Tricks](https://css-tricks.com). Their explanations are very thorough and it is a good site for reference.

## Centering Boxes
For centering text within a container, the CSS property ```text-align: center``` can be used. This has the same effect as clicking the "Center" button in your word processing software. However, items like YouTube embeds are not text, and can't be centered in the same way. To center a box within another box (like an ```iframe``` on a page or in a ```div```), left and right margins can be used with the ```auto``` setting, **as long as you explicitly set a height and width**. Specifically, you can use CSS like this.

	.center{
		margin-left: auto;
		margin-right: auto;
	}

or the equivalent

	.center{
		margin: 0 auto;
	}

See this example:

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="result" data-user="mjsamberg" data-slug-hash="poNRKdW" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="ECI 519 - Automargins">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/poNRKdW">
  ECI 519 - Automargins</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

## Floats

In traditional desktop publishing, the ability to "pull" assets to the left and right of the page to create things like callout boxes or similar layout elements. In CSS, we can accomplish this with the ```float``` object. By specifying a value of left or right, the box will be pulled to the left or the right of its container (either the page, or a container element). If the width of the box is less than 100%, that creates a CSS callout box. [Read more at CSS Tricks](https://css-tricks.com/all-about-floats/) and review the example below.

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="result" data-user="mjsamberg" data-slug-hash="xxRgzwz" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="ECI519 - Unit 4 - Floats">
	  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/xxRgzwz">
	  ECI519 - Unit 4 - Floats</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
	  on <a href="https://codepen.io">CodePen</a>.</span>
	</p>

## Absolute Positioning

Absolute positioning means that you can place an element at a specific place on a page. For example, if your CSS had the following code:

	.absolute-center{
		position: absolute;
		top: 50%;
		right: 50%;
	}

your element with the ```.absolute-center``` class would be exactly in the physical center of the page, 50% from the top and 50% to the right. This can lead to some unexpected results, such as overlapping or hidden elements. However, using a combination of ```relative``` and ```absolute``` positioning, it's possible to position elements in specific points inside their containers. [Read more at CSS Tricks.](https://css-tricks.com/absolute-positioning-inside-relative-positioning/)

## Flexbox and Grid

```Flexbox``` and ```Grid``` are two relatively new constructs in CSS. To a large extent they solve similar problems - they make it easy to create boxes in boxes that look uniform, while taking the guesswork out of it. Consider a deck of cards. Either flexbox or grid allow you to place each card on the table and the CSS will automatically take care of making sure the cards look right. Grid [is better for large layouts and used much less](https://css-tricks.com/snippets/css/complete-guide-grid/). However, you should be familiar with Flexbox as it solves many problems, including making vertical centering very easy, making sure that cards are all the same size, and that cards fill the space available or wrap where needed. You should be familiar with Flexbox and the advantages it offers.

Review the [CSS Tricks tutorial on Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/), and don't forget to expand the "Background" and "Basics & Terminology" sections at the top of the page. Review the examples on the page.


<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>