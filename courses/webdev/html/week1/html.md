---
layout: page
title: "An Overview of HTML"
course: "webdev"
unit: 2
---
A "markup language" is a tool used to annotate text entry in the computer so that a computer can format the text correctly. Markup languages are the way that all text input is stored behind the scenes in the computer (your [Word Documents use a markup language](https://docs.microsoft.com/en-us/openspecs/ie_standards/ms-xml/987c45e5-aa50-4bf6-a82a-dec921c71ad5) as well, but it is hidden from you by the Word GUI). In the times before GUIs, it was necessary to include your markup manually in word processors such as WordPerfect and others. 

HyperText Markup Language (HTML) is the basis of all web pages and content on the Internet. "HyperText" is a term that implies that text can be interconnected by hyperlinks, or links between pages that are navigated via the mouse and keyboard. The term "hypertext" was [coined around 1965](https://www.w3.org/History.html). 

The HTML is defined and managed by the [Word Wide Web Consortium](https://www.w3.org) - a membership body that creates and manages the standard HTML that is used across the web. By being a non-profit standard, any web browser company may access the standard, parse it, and render it in similar ways to other standards. This means that HTML is HTML regardless of whether you're using Chrome or Firefox or the browser built in to your TV. 

The most current version of the HMTL standard is 5.2, released in 2017. The HTML standard has evolved significantly since version 1.0 as the speed of Internet connections and computers has increased (HTML 1, for example, had rudimentary image support and no interactive components). Additionally, all styling of HTML had to be done with in the HTML itself, with support for Cascading Stylesheets (CSS), being introduced around 2007 (we will dive deeply into CSS in a few weeks). The result was the [simplistic websites we tend to associate with the 90s](https://www.justinmind.com/blog/10-90s-websites-designs-you-wont-believe-existed/). 

## HTML Structure
HTML uses "tags" which are specific phrases, surrounded by less-than/greater-than signs. The first tag is called the "opening tag" and the second tag is a closing tag. For example, if I wanted to _emphasize some text on my page_, I would use the `em` tag. Between the opening and closing tag is the content to be emphasized. So it would look like this:

    <em>Text to be emphasized</em>

The slash on the closing tag is the symbol to indicate that it is a closing tag. HTML tags are always written in lowercase, since HTML 4.0. 

Some elements have attributes as well. For example, creating a link has several attributes:

	<a href="http://www.google.com">Go to Google!</a>

The ```a``` tag defines the tag as a link. the ```href``` attribute describes the target for the link. The link text between the opening and closing tags defines the text that will be rendered. The result will be this link:

<a href="http://www.google.com">Go to Google!</a>

## The DOM Model
Web pages are structured according to the _Document Object Model_ (DOM). 
<div class="text-center">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/DOM-model.svg/1200px-DOM-model.svg.png" alt="Document Object Model" style="max-width: 50%;">
</div>

The DOM is a fancy way of saying that elements contain attributes and text, but may also contain other attributes. Elements that are within elements must be completely contained in the element. For example, if we wanted our "Go to Google!" link to be emphasized with some text after it, we would need to contain the ```em``` tag completely within the ```a``` tag. Therefore, this is valid:

	<a href="http://www.google.com"><em>Go to Google</em></a> <em>and search because Google is a search engine.</em>

and this is valid:

	<em><a href="http://www.google.com">Go to Google</a> and search because Google is a search engine.</em>

however, this HTML is not valid:

	<a href="http://www.google.com"><em>Go to Google</a> and search because Google is a search engine.</em>