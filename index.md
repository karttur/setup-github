---
layout: default
title: Setup GitHub pages
date: '2017-12-25 11:56'
---
**Contents**
	- [Introduction](#introduction)
	- [Setup GitHub](#setup-github)
		- [Create a Repository](#create-a-repository)
		- [Create a branch](#create-a-branch)
		- [Your first GitHub web pages](#your-first-github-web-pages)
	- [Markdown and layout using Atom](#markdown-and-layout-using-atom)
		- [Replace index.html with index.md](#replace-indexhtml-with-indexmd)
		- [Create Jekyll configuration](#create-jekyll-configuration)
		- [Commit and push your changes](#commit-and-push-your-changes)
	- [Linking a Cascaded Style Sheet (CSS)](#linking-a-cascaded-style-sheet-css)
	- [Resources](#resources)

## Introduction

In my [previous blog](/setup-blog/2017/12/21/setup-blog-tools.html) I set up [Jekyll](https://jekyllrb.com) and [Atom](https://atom.io) for creating my first blog. To do so I used the Jekyll default theme (minima). But I wanted to have a better understanding of how Jekyll tags and commands work, and to publish my blog on [GitHub.com](https://github.com). This blog is thus created without any template and only contain a very simple, single blog post written in markdown <span class ='file'>index.md</span> in the blog (repository) root directory.

[GitHub.com](https://github.com/) is a web based version control _repository_ service. It is primarily used for program code, but can be used for any document tracking, and for publishing web pages. To keep track of different versions and edits of documents (codes, projects etc), GitHub stores different versions and edits in _branches_. By default, each repository contains a branch called 'master' where the latest operational version of your project is hosted.

To use GitHub for publishing web-pages, all you have to do is to create a special, stand alone, branch with the pre-defined name 'gh-pages'. GitHub will take files found in 'gh-pages' and convert them into static html pages. You can publish simple text files or ordinary html coded files via the 'gh-pages'. But the real strength comes with using markdown (or md) coded files, that are converted by GitHub to html coded files. Markdown files are much easier to work with compared to html coded files, and can yet be used for creating advanced web pages.

GitHub provides a special application, Jekyll for creating web pages using markdown. This blog will go through setting up GitHub, publishing a static html file, and creating and publishing markdown files using Jekyll. How to install Jekyll and the text editor Atom (for writing markdown file), is the topic of the [previous blog](/setup-blog/2017/12/21/setup-blog-tools.html).

## Setup GitHub

This blog uses the [GitHub desktop.app](https://desktop.github.com/) for setting up a GitHub.com account, and managing and publishing GitHub pages. Alternatively it is also possible to set up your account directly on GitHub.com, and use the Terminal for managing and publishing.

Download and Install [GitHub desktop.app](https://desktop.github.com/).

Start <span class='app'>GitHub desktop.app</span> and create your own GitHub user account on GitHub.com from the <span class='app'>GitHub desktop.app</span>. When your account is created, log in to it; you can access it either from the <span class='app'>GitHub desktop.app</span>, or log in by going to [GitHub.com](https://github.com/) in your web browser.

### Create a Repository

You can create a repository either from the <span class='app'>GitHub desktop.app</span> or directly in GithUb.com. In the first case you need to publish the repository to GitHub.com, in the latter you have to clone the online repository to your local computer. In both cases you will end up having two clones of your repository, one online (at GitHub.com) and one on you local computer. This blog describes how to create the repository using the <span class='app'>GitHub desktop.app</span>.

In the <span class='app'>GitHub desktop.app</span> go via the menu:

<span class='menu'>File : New Repository</span>

Enter a name ('setup-github') and a description. To create a new repository you have to enter a <span class='textbox'>Local Path</span> in the text box, if you create the path using the <span class='button'>Choose</span> button, <span class='app'>GitHub desktop.app</span> will treat it as an existing local repository to Add (rather than Create). You can leave <span class='textbox'>Git Ignore</span> and <span class='textbox'>License</span> to None. Click <span class='button'>Create Repository</span>.

In the top menu, you now have to click <span class='tab'>Publish repository</span>. In the window that opens, un-check <span class='textbox'>Keep this code private</span>, and click <span class='button'>Publish Repository</span>. By default the <span class='tab'>Branch</span> tab in the top menu will say 'master'.

If you check your online GitHub.com account, your new repository should appear after a few minutes. You might need to refresh your web pages to see it

### Create a branch

In order to publish your own web-pages on GitHub, you have to create a special branch called 'gh-pages'.

Open <span class='app'>GitHub desktop.app</span>, In the top menu you should see three alternatives:

<span class='tab'>Current Repository : Current Branch : Fetch original</span>

To create a new branch click on the little expansion triangle to the right of the text <span class='tab'>Current Branch</span>. In the drop down menu that appears, click <span class='button'>New</span>, and enter 'gh-pages' (without quotation) in the <span class='textbox'>Name</span> text box, and click <span class='button'>Create Branch</span>. The <span class='tab'>Current Branch</span> should now indicate that 'gh-pages' is your current branch. For GitHub to put the new branch to your online repository at GitHub.com, you must also click the new <span class='tab'>Publish Branch</span> tab in the top menu of GitHub desktop.app.

Once you have published a branch, the <span class='tab'>Publish Branch</span> tab will  be replaced by a tab that instead says either <span class='tab'>Fetch origin</span> or <span class='tab'>Push origin</span>. Every time you commit a change, the tab will change to <span class='tab'>Push origin</span>, and you must click it in order for GitHub to push the committed changes to your online GitHub.com branch (as indicated in the <span class='tab'>Branch</span> tag).

### Your first GitHub web pages

At this stage you must create a very simple file called <span class='file'>index.html</span>, and put it in the local copy (clone) of your GitHub repository. If you do not have a suitable text editor, use the [previous blog](/setup-blog/2017/12/21/setup-blog-tools.html) to download and install <span class='file'>Atom</span>. The file (<span class='file'>index.html</span>) should only contain text (no html code). For example:

```
My first GitHub page.
```

Return to the <span class='app'>GitHub desktop.app</span>, where you should now see  <span class='file'>index.html</span> in the list under the <span class='tab'>Changes</span> tab (in the row below the top menu). Before you can commit the <span class='tab'>Changes</span>, you **must** write a <span class='textbox'>Summary</span> (and better also a <span class='textbox'>Description</span>). Once you have entered a summary, the <span class='button'>Commit to gh-pages</span> button at the bottom will clear (if the button does say 'master' instead of 'gh-pages', you must change, or create, the branch 'gh-pages' as described in the previous section). Click <span class='button'>Commit to gh-pages</span> to commit your changes.

The list in the <span class='tab'>Changes</span> tab should clear. To push the committed files to the repository, you must also Click <span class='tab'>Push origin</span> in the top menu.

It will take up to 10 minutes for GitHub to receive and publish the changes. Go to your account in GitHub.com (use your web browser) and navigate to the repository (in my case 'setup-github') you are working with. Find the <span class='button'>Branch</span> button, and click it to change to the 'gh-pages' branch. The file <span class='file'>index.html</span> should appear. If not, refresh the page, and make sure you did click <span class='tab'>Push origin</span> in the top menu of the <span class='app'>GitHub Desktop.app</span>.

When the file <span class='file'>index.html</span> appears under the branch 'gh-pages' in your GitHub.com account, you can view your page under the url address:
```
http://'yourGitHubUser'.github.io/'repository'
```

where 'yourGitHubUser' is the name of the GitHub account you created, and 'repository' is name of the repository ('setup-github' in my case) that you first cloned and then added the file (index.html) to. The web page will be a single paragraph, regardless the length of your text.

When you make any changes to your local clone of <span class='file'>index.html</span>  (or any other file in the local clone folder of your GitHub repository), the changed or added files will appear under the <span class='tab'>Changes</span> tab in the <span class='app'>GitHub desktop.app</span>, and you have to repeat commit and push origin in order to transfer the files to your GitHub.com online repository.

## Markdown and layout using Atom

You can use any text editor to follow the rest of this blog, but the detailed commands are written for Atom. How to install and set up Atom is described in the [previous blog](/setup-blog/2017/12/21/setup-blog-tools.html).

Start <span class='app'>Atom</span>, and go via the main menu:

<span class='menu'>File : New window</span>

The <span class='tab'>New Window</span> will open with some default tabs, including the <span class='tab'>Welcome Guide</span>. Click it and select 'Open a Project', and then click the button that also says <span class='tab'>Open a project</span>. Navigate to the folder containing the local clone of your GitHub repository, and select the folder to be your Project.

In the Atom <span class='tab'>Project</span> pane that opens you should see the <span class='file'>index.html</span> file that you created above. You are going to change the file from html to markdown, and add some markdown codes.

### Replace index.html with index.md

To rename <span class='file'>index.html</span> to <span class='file'>index.md</span>, select it in the Atom <span class='tab'>Project</span> pane and ctrl-click (or left click) on your track pad or mouse; in the list that appears, select <span class='menu'>Rename</span> and change the extension from .html to .md.

Open <span class='file'>index.md</span> in Atom by just clicking on it in the <span class='tab'>Project</span> pane. Replace the content of <span class='file'>index.md</span> with the following:
```
---
layout: default
title: Setup GitHub pages
date: '2017-12-25 11:56'
---

## My first heading

[Other web page](url) is my _favorite_ site for ...

```
The code embraced by the triple hyphens (---) defines the front matter, and is called YAML as the jargon goes. YAML can contain a lot more, but we will just set layout, title and date. You should keep the YAML exactly as it is. \#\# is the markdown code for <h2> (header level 2), the markdown code \[\]\(\) is for linking a url, and the underscore (\_) enclosure is the markdown code for _italic_ fonts.

Save the edits by going via the <span class='app'>Atom</span> main menu:

<span class='menu'>File : Save</span>

To add layout, and header and footer to your web page you first need to add two subfolders in your repository. You can use <span class='app'>Atom</span> in a similar manner as when you renamed the file above. Select the project top folder ('setup-github') and ctrl-click, in the list that appears select <span class='menu'>New Folder</span>. Create a folder named <span class='file'>\_layouts</span>. Repeat and create another folder named <span class='file'>\_includes</span>.

Create a new file using <span class='app'>Atom</span>, go via the main menu:

<span class='menu'>File : New File</span>

An empty file opens. Copy and paste the following code to the empty file:
{% raw %}
```
{% include header.html %}
    <h1>{{ page.title }}</h1>
    {{ content }}
{% include footer.html %}
```
{% endraw %}
And save it in the <span class='file'>\_layouts</span> folder as <span class='file'>default.html</span>:

<span class='menu'>File : Save</span>

To understand the code a bit, a quick explanation is required:

The include tag
{% raw %}
```
{% include header.html %}
```
{% endraw %}

looks for a file in the <span class='file'>\_includes</span> folder with the indicated name (footer.html) and inserts it in place of the include tag itself.

The double curly braces are instead replaced by the text that is referred to. In the file <span class='file'>default.html</span> above, the tag
{% raw %}
```
{{ content }}
```
{% endraw %}
is replaced by the _content_ of index.md, following the YAML code, and the tag
{% raw %}
```
{{ page.title }}
```
{% endraw %}

is replaced by the YAML title given in index.md.

The files <span class='file'>header.html</span> and <span class='file'>footer.html</span> referred to in <span class='file'>default.html</span> do not exist. You need to create them and put them in the subfolder <span class='file'>\_includes</span>. <span class='file'>header.html</span> should contain the following text:

```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>{{ page.title }}</title>
        <link rel="stylesheet" href="{{ site.baseurl }} css/styles.css" >
    </head>
    <body>
```

And <span class='file'>footer.html</span> should contain this text:

```
  </body>
</html>
```

### Create Jekyll configuration

Finally you have to create the Jekyll configuration file <span class='file'>\_config.yml</span>, directly under the Project (or repository) folder (in my case <span class='file'>setup-github</span>). Copy and paste the following content to it:
```
name: My first GitHub page
markdown: kramdown
rouge: true
baseurl: ""
```

### Commit and push your changes

Return to <span class='app'>GitHub desktop.app</span>, all the files you have created should be listed under the <span class='tab'>Changes</span> tab. Enter a <span class='textbox'>Summary</span> and a <span class='textbox'>Description</span>, and click the <span class='button'>Commit to gh-pages</span> button (details above). Then click the top menu tab <span class='tab'>Push origin</span> that appears after you committed the files.

Open your web browser and return to your online GitHub.com account. Wait for the files to appear in the 'gh-pages' branch. When they appear, you can open (or refresh) your own web page:
```
http://'yourGitHubUser'.github.io/'repository'
```

### Linking a Cascaded Style Sheet (CSS)

So far the web page does not contain any style (CSS), even if the <span class='file'>header.html</span> has a link to a CSS file.
```
<link rel="stylesheet" href="{{ site.baseurl }} css/styles.css" >
```
For this web page I copied the style sheet that was created in the [previous blog](/setup-blog/2017/12/21/setup-blog-tools.html), and saved it as <span class='file'>/css/styles.css</span> under my repository root folder. I then also copied the top banner with the text 'Geo Imagine Developer' and the About link. And then I did the same thing for page trailing content.

I finally used the package markdown-toc to generate the table of contents. And then I commited and pushed my local repository to my GitHub.com account.

### Cleanig up repository

When I committed and pushed the repository I discovered that it contained an internal macOS file (<span class='file'>.DS_Store</span>) and redundant folder (<span class='file'>\_drafts</span>) and <span class='file'>\_site</span>). To remove them from the repository I first created a <span class='file'>.gitignore</span> using the Terminal:

<span class='terminal'>$ touch .gitignore</span>

Despite being a hidden file (starting with a dot[.]) it can be seen and edited in <span class='app'>Atom</span>, and you have to enter the files and folders that git should ignore.
```
.DS_Store
_site/
_drafts/
```
The <span class='file'>\_site</span>) folder is recreated each time you start Jekyll, and it will also the created automatically from the 'gh-pages' branch at GitHub.com, and published as a web-site (you will not see them inside your repository though).

In the <span class='app'>Atom</span> <span class='tab'>Project</span> pan, the files and folders in <span class='file'>.gitignore</span> will change color, indicating that they are ignored by git.

As the file and the folder were already in the GitHub.com repository, I had to remove them 'manually', also using the terminal. Deleting the files are folders is easier in either <span class='app'>Finder</span> or <span class='app'>Atom</span>, but you can also do it using the <span class='app'>Terminal</span>:

<span class='terminal'>git rm --cached \_drafts/'filename'</span>

and

<span class='terminal'>git rm --cached .DS_Store</span>

I then actually had to make an edit to one of the other files in the repository in order for <span class='app'>GitHub desktop</span> to understand that I wanted to commit and push the changes. Then I got rid of the unwanted files and folders in the online repository.

If you want to see the files used for building this blog, the [completed repository](https://github.com/thomasgumbricht/setup-github/tree/gh-pages) is available on GitHub.com.

## Resources

[Jekyll](https://jekyllrb.com/docs/home/)

[Get Started With GitHub Pages](https://24ways.org/2013/get-started-with-github-pages/) by Anna Debenham

[How to Upload Jekyll to Github Page](https://www.hongkiat.com/blog/jekyll-github-pages/) by Thoriq Firdaus

[This blog on GitHub.com](https://github.com/thomasgumbricht/setup-github/tree/gh-pages)

[Set up blog tools: Jekyll and Atom](/setup-blog/2017/12/21/setup-blog-tools.html) my previous blog
