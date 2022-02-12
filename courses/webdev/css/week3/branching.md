---
layout: page
title: "GitHub Branching and Assignment"
course: "webdev"
unit: 6
---

A _branch_ in GitHub is used to develop a new feature or work in GitHub without impacting your main branch. This allows you to make changes to your code, store them in GitHub for safekeeping or collaboration, and not impact the rest of the codebase (or if you're hosting your website on GitHub, what other people see on your website). 

When you create a branch in GitHub, you start with a copy of another branch (i.e., Master). You can make all of the changes you want in your new branch. When you're done, you can either keep that branch separate, or _merge_ all of your changes back in to your Master branch. [Video overview](https://www.youtube.com/watch?v=2GO1a1vgNrc)

## Assignment
Your assignment this week is to deploy the Bootstrap framework to your website:
1. Create a new branch for your work in GitHub Desktop. Call it "Bootstrap". To do that, click in GitHub Desktop, click on "Current Branch" in the toolbar, and select "New Branch". Create your branch.
2. Empty the contents of your CSS file and remove all classes from your HTML files. Don't worry, GitHub keeps backups...
3. Modify your website in order to integrate the bootstrap elements. You should use one bootstrap layout element (i.e. columns), one text formatting component (i.e. margins or padding to replace what you were doing via CSS already), and one semantic element. Add additional formatting to your CSS as needed to supplement what Bootstrap gives you by default.
4. Commit and push the new branch to GitHub by clicking "Publish Branch" in GitHub Desktop.
5. In GitHub, click on "Settings", and "Pages". Under "Source", change the branch to use your new Bootstrap branch. Save changes and your site will now use your new code.