---
layout: page
title: "Writing Clean (and Happy) Code"
course: "webdev"
unit: 2
---

The biggest way to save yourself time in managing a website is to write clean code. The biggest mistake people make at this stage of web development is not closing tags that they open, resulting in unexpected formatting. A few simple rules can help you avoid these mistakes.

## Rule 1: Contain your Containers
On the previous page, we learned about three types of containers: content sections, text sections, and text formatting. To avoid unexpected displays, think about these like a hierarchy. All text formatting tags should be within sections and all text sections should be within content sections. For example, this is valid HTML:

	<div>
		<p><em>My emphasized text.</em></p>
	</div>

but this can be messy in a lot of situations:

	<em>
		<article>
			<p>My emphasized text.</p>
		</article>
	</em>

While it would render, it would make formatting complex projects exceedingly difficult - the goal is to flow from general formatting to specific formatting and. Sometimes this may be duplicative. While:

	<article>
		<em>
			<p>My emphasized paragraph.</p>
			<p>Another emphasized paragraph.</p>
		</em>
	</article>

would work in your browser and it seems simpler, it does create complications with more complex documents. Always go from content sections to text sections to text formats, even if it means you have to be duplicative:

	<article>
		<p><em>My emphasized paragraph.</em></p>
		<p><em>Another emphasized paragraph.</em></p>
	</article>


## Rule 2: Nesting
HTML tags are nested, meaning that in the DOM model, tags fall within other tags. The easiest way to preserve this is to make sure to close tags in the reverse order you open them. For example:

	<p><em>My emphazied text</em></p>

is clean HTML, but 

	<p><em>My emphasized text.</p></em>

could cause problems if you are trying to make sure tags are closed, or if you need to add some text to your paragraph that should not be emphasized. It also breaks the specification of the Document Object Model which specifies that all containers should be contained inside other containers. 

### Rule 3: Indent
In most programming languages, HTML included, white space (tabs and spaces) at the beginning of a line are ignored. This allows you to use them to format your code to make sure it looks clean. You should indent with a tab or with four spaces at the beginning of a line (Visual Studio and many editors will do it for you automatically). As a rule, if you open a container tag that will span multiple lines, the tag should be on a line by itself, and everything between the opening tag and closing tag should be indented with tabs or four spaces. Whether you use tabs or spaces is a [personal preference](https://youtu.be/cowtgmZuai0) that's the subject of [fanatical debate](https://www.businessinsider.com/tabs-vs-spaces-from-silicon-valley-2016-5), it doesn't really matter which one you use as long as you're consistent. 

Without using whitespace, you end up with something that looks like this:

	<main><p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <em>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</em> Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p></main>

By using whitespace, it's a little better:

	<main>
	<p>
	Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <em>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</em> Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
	</p>
	</main>

But whitespace with tabs and spaces produces something much more readable:

	<main>
		<p>
			Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <em>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</em> Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
		</p>
	</main>

Note that newlines aren't necessary for tags that format text. Also, adding whitespace in your text is optional. In VS Code, you can turn Word Wrap on or off in the settings and it will wrap long strings of text for you.

### Rule 4: Add Comments
You can add comments in your HTML. A comment is something that is visible in the HTML code, but won't render in the browser. Use them to leave reminders for you or other coders about how things need to be set up. Comments use a tag structure as follows: ```<!-- I need to include important text in the next section -->```

### Rule 5: Validate and Format
Visual Studio Code has tools built in that will [validate and format](https://code.visualstudio.com/docs/languages/html#_validation) your code for you.
