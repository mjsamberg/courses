---
layout: page
title: "JavaScript API Examples"
course: "webdev"
unit: 9
---

JavaScript APIs and Frameworks are like libraries, but more opinionated. They're incredibly powerful, and have advantages over embedding content, namely that you can use JavaScript controls on your page to interact with the elements (i.e. [YouTube's JavaScript API](https://developers.google.com/youtube/iframe_api_reference) allows you to control the embedded video player using elements native to your HTML page. This page has two examples:

## [Desmos](https://www.desmos.com/api/v1.5/docs/index.html)

Desmos is a graphing calculator app. Their documentation is very good, with lots of examples. Here's a quick CodePen with a form that inputs an equation an then graphs it:

<p class="codepen" data-height="700" data-theme-id="dark" data-default-tab="result" data-user="mjsamberg" data-slug-hash="JjEPjxw" style="height: 700px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Unit 9 - Desmos">
  <span>See the Pen <a href="https://codepen.io/mjsamberg/pen/JjEPjxw">
  Unit 9 - Desmos</a> by Mark Samberg (<a href="https://codepen.io/mjsamberg">@mjsamberg</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## [RevealJS](https://revealjs.com)
RevealJS is a bit different because it doesn't use Bootstrap or anything else, it's completely self-contained. There is no CDN, just download it from their site and go (see [Basic Setup Options](https://revealjs.com/installation/)).

RevealJS allows you to use HTML to create embeddable slideshows. For example:

<iframe class="embed-responsive-item" src="https://mjsamberg.github.io/resourceguides/accessibility/presentation.html"  width="600" height="600"></iframe>

The source code for this is located at [https://github.com/mjsamberg/resourceguides/tree/master/accessibility](https://github.com/mjsamberg/resourceguides/tree/master/accessibility).