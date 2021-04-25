---
layout: page
title: "Moving Your Site"
course: "webdev"
unit: 13
---

The site you've created so far exists in a class-level GitHub account. It will be archived at the end of the course and will become inaccessible. While we've done some basic work in GitHub, there are [so many features](https://www.youtube.com/watch?v=RGOj5yH7evk) that we've yet to explore. While GitHub's primary use is for hosting source code for full-stack applications (front-end applications, back-end services, and combinations of both), it also can be used as a free way to host front-end websites as we have been doing this semester. 

## Setting Up a New GitHub Repository
In order to build a new GitHub repository outside of the course to host your website, follow these steps:
* Go to [GitHub.com](https://github.com)
* Make sure you're logged in
* Click **New** next to _Respositories_ at the upper right
* Ensure that you are listed as the _Owner_ of the repository, and give the repository a name. See the "Important note about naming repositories" below.
* Ensure that it's listed as **Public**
* Click **Create Repository**
* On the page that comes up, find the heading that reads _Quick Setup - if you've done this kind of thing before_ and copy the URL in the box on the left.

Now that you've set up a repository, let's push our site to it:
* In GitHub Desktop application, go to the _Repository_ menu and select _Repository Settings_.
* In the field that reads _Primary Remote Repository_, paste the URL you copied above, overwriting what's there.
* Go to the _Repository_ menu and select _Push_.
Your site should now be in the new repository.

Last step: we need to set up GitHub to host your site. Back on the GitHub website:
* Click _Settings_
* Select _Pages_ from the sidebar
* Change _Source_ to your **Master** or **Main** branch.
* Click _Save_. The website should display your URL and be ready to be viewed within a few minutes.

### Important note about naming repositories
By default, your repository will have the URL ```http://[username].github.io/[repository_name]```. You can set GitHub to automatically set a website to be your default website at ```http://[username].github.io``` by naming your repository ```[username.github.io]``` (for example, mine would be ```mjsamberg.github.io```). That means that users would need a subdirectory to get to that site. 

## Purchasing a Domain Name
In addition to a ```github.io``` URL, you can buy your own domain name (```myawesomeeci519website.com```) and use it for GitHub with no additional charges beyond the purchase of the domain name (generally around $15/year). In the GitHub pages setup, you can specify your custom domain to be used and then head over to a site like [Google Domains](https://domains.google) or [GoDaddy](https://www.godaddy.com) to purchase your domain name. Once you purchase the domain name, you have to add the records to point the domain name to GitHub Pages ([Instructions for Google Domains](https://dev.to/trentyang/how-to-setup-google-domain-for-github-pages-1p58)).

## Other Hosting Options
Other sites, like GoDaddy offer hosting options as well. If you want to host there, simply follow the instructions to upload your site files to those sites.