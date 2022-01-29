---
layout: page
title: "Linking"
course: "webdev"
unit: 3
---
<a id="intro"></a>
One of the key features of Hypertext documents is the ability to link between documents. Links in HTML use the ```<a>``` tag. ```<a>``` stands for _anchor_, as in, anchoring to another page. A very basic link has a single attribute, ```href``` which defines the target for the link (the page that is to be linked to). There are other attributes for the ```<a>``` tag which we will explore below. There are other places where the ```href``` attribute is used, largely in JavaScript applications that we will discuss later in the course and in in-page anchors in HTML 4 and below. 

So a basic link looks like this:

	<a href="http://www.ncsu.edu">This is a link to NC State University</a>

and would produce
<a href="http://www.ncsu.edu">This is a link to NC State University</a>.

## Relative Links
A "relative link" is a link that points to a destination on the same website or server without using a full URL. This is useful because it allows a website to be moved easily without having to update links (for example, you can develop a website on your computer and then publish to GitHub and everything still works). Consider the following directory structure. When mapping directories, we use a "/" after the name to define a folder, use a "/" to define the top-level of our website:

	--/
	-- -- index.html
	-- -- bio.html
	-- -- blog/
	-- -- -- index.html
	-- -- -- post1.html
	-- -- -- post2.html

If you wanted to link from ```index.html``` to ```bio.html``` the entire URL is unnecessary, you would just have to include the name of the webpage: ```<a href="bio.html">My Bio</a>```. If you wanted to link to the blog post, you would include the directory name as well: ```<a href="blog/post1.html">My First Blog Post</a>```. 

If you were on the ```post1.html``` page and wanted to include a _Return Home_ link, you would include ```../``` at the beginning of your URL - this tells your browser to "go up one level": ```<a href="../index.html">Return Home</a>```. If you had a more complicated webpage directory layout you can stack the ```../``` to go up multiple levels (for example, if you had a page at ```/blog/entries/post1.html```, your link would be ```<a href="../../index.html">Return Home</a>```).

The ```index.html``` page is always used as the default and is not necessary to include in a URL (though it's not necessarily a bad idea). ```<a href="blog">My Blog</a>``` and ```<a href="blog/index.html">My Blog</a>``` will point to the same page.

The temptation (and the Bad Code Trap) that some people fall into is to shortcut this by using the ```/``` at the beginning of a URL to shortcut this process. For example ```<a href="/index.html">Return Home</a>``` would technically be valid anywhere on your site and would return you to the home page no matter how many levels deep you were. However, the ```/``` denotes the root URL of the *domain* you're using, not the website. Therefore on this site: ```<a href="/">Return Home</a>``` would point to ```http://mjsamberg.github.io``` and not ```http://mjsamberg.github.io/courses```. Some people may shortcut this by using ```<a href="/courses">Return home</a>```. That's fine until I decide to move ```http://mjsamberg.github.io/courses``` to ```http://www.sambergcourses.com``` in which case all of my links are now broken. As a rule, you relative links should always be relative to your current location.

### On Filenames and Directory Names
Now is a good time to mention naming conventions for all web files (HTML files, images, etc.). By default, neither a directory name nor a filename on a website cannot have spaces in it. Also, some web servers are case sensitive, so it is a best practice to only use lowercase file names. Dashes can be used in lieu of spaces if needed, but other special characters may not be used - only letters and numbers and a file extension (i.e. .html).

## Link Targets
The default behavior for links is that they should open in the same window that you're currently viewing a page in. That's typically fine when a user is browsing your site, but if they're going to an external site, it may not be - you may want external links to open in the same window. That's where the ```target``` attribute comes in. While there are other uses for this attribute that are used in embedding documents, setting the ```target``` attribute to ```_blank``` will open in the link in a new window (or tab, depending on browser settings). Example:

	<a href="http://www.ncsu.edu" target="_blank">NC State, In a new window</a>

yields: <a href="http://www.ncsu.edu" target="_blank">NC State, In a new window</a>

## Relationship Types
The ```rel``` attribute in a link defines the relationship that the link has to the original page. For example, ```<a href="help.html" rel="help">Help</a>``` would tell a browser that this is the link to a help page. The [full list of attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types) is available - though most are seldom used. The important one is ```rel=nofollow```. Search engines index sites by following links. If a page is private then you should, among other security measures, set this flag to prevent a search engine from trying to index the page.

## Special Links
There are a few types of special link types that you can include. ```mailto:``` links will open an email in your default email client:

	<a href="mailto:user@example.com">Mail Example User</a>

yields a link <a href="mailto:user@example.com">Mail Example User</a>. The ```tel``` and ```sms``` URL schemes accept phone numbers and will open a telephone dialer or a text message, respectively. A country code is required (+1 for the USA):

	<a href="tel:+19195551212">Call</a> or <a href="sms:+19195551212">Text</a>

yields: <a href="tel:+19195551212">Call</a> or <a href="sms:+19195551212">Text</a>

You can add parameters to these as well. After the email address, for example you can add a subject line and email body like so:
	```<a href="mailto:user@example.com?subject=My&nbsp;Email&nbsp;Subject&body=This&nbsp;is&nbsp;the&nbsp;body&nbsp;of&nbsp;my&nbsp;email&nbsp;message.">Email me an example</a>```
yielding: <a href="mailto:user@example.com?subject=My&nbsp;Email&nbsp;Subject&body=This&nbsp;is&nbsp;the&nbsp;body&nbsp;of&nbsp;my&nbsp;email&nbsp;message.">Email me an example</a>. The ```nbsp&``` character is an HTML character entity for a space since URLs cannot have spaces in them.

You can do the same with an SMS message, with ```<a href="sms:+19195551212&body=Is&nbsp;school&nbsp;closed&nbsp;today?">Send text</a>``` yielding <a href="sms:+19195551212&body=Is&nbsp;school&nbsp;closed&nbsp;today?">Send text</a>.

## In-Page Links
If you have a long page (like an FAQ page), sometimes it's good to be able to have links to different points on the page (like a list of questions that link to responses further down, or a link that returns to the top of the page).

You can do this by adding an ```id``` attribute to any container element on a page. For example, at the top of this page, I have a section tag ```<section id="intro">```. If you want to link from this from within the page (or from any other page), all I would need to do would be to have a link ```<a href="links.html#intro">Return to Intro</a>``` which would yield <a href="links.html#intro">Return to Intro</a>.

## [Supplemental Reading](https://www.w3schools.com/html/html_links.asp)
