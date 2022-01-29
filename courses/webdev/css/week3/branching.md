---
layout: page
title: "GitHub Branching and Assignment"
course: "webdev"
unit: 6
---

A _branch_ in GitHub is used to develop a new feature or work in GitHub without impacting your main branch. This allows you to make changes to your code, store them in GitHub for safekeeping or collaboration, and not impact the rest of the codebase (or if you're hosting your website on GitHub, what other people see on your website). 

When you create a branch in GitHub, you start with a copy of another branch (i.e., Master). You can make all of the changes you want in your new branch. When you're done, you can either keep that branch separate, or _merge_ all of your changes back in to your Master branch. [Video overview](https://www.youtube.com/watch?v=2GO1a1vgNrc)

To create a new branch in GitHub Desktop, [follow these instructions](https://idratherbewriting.com/learnapidoc/pubapis_github_desktop_client.html#merge-the-development-branch-into-master). Typically, in a large group, you would marge via Pull Request to give others the ability to comment on the merge before it takes place. However, when you're working individually on your own code, you would typically merge directly.

## Assignment
Your assignment this week is to deploy the Bootstrap framework to your website:
1. Create a new branch for your work in GitHub Desktop. Call it "Bootstrap".
2. Empty the contents of your CSS file. Don't worry, GitHub keeps backups...
3. Modify your website in order to integrate the bootstrap elements. You should use one bootstrap layout element (i.e. columns), one text formatting component (i.e. margins or padding to replace what you were doing via CSS already), and one semantic element. Add additional formatting to your CSS as needed to supplement what Bootstrap gives you by default.
4. Commit and push the new branch to GitHub.
5. If you plan to use the Bootstrap branch moving forward (definitely recommend), merge the Bootstrap branch back to Master and push that change to GitHub. If you do not plan to use Bootstrap in the future, on the GitHub website, navigate to the settings page. Under GitHub Sites, change it to use your new Bootstrap branch. Once the assignment has been graded you can change it back.