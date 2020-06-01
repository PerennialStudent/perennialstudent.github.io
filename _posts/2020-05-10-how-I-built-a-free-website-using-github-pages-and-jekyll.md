---
layout: post
title:  "How I built a free website using GitHub Pages and Jekyll, with no prior knowledge in web-building"
#author: sal
categories: [ Jekyll, GitHub, tutorial ]
image: assets/images/2020/website-screenshot.png
beforetoc: "A condensed review of how I built my website."
toc: true
featured: true
comments: false
---

## Motivation
> "How can I create a fully functional and customisable website for free?

> I am not a professional programmer, how can I build my own website without relying on commercial web-builders like WordPress or Wix?"

To address the above questions, this post outlines how I created a personal website using GitHub Pages and Jekyll.

Most of the materials in this tutorial were compiled from the [Jekyll website](https://jekyllrb.com/) and this helpful [Youtube series](https://youtu.be/T1itpPvFWHI).

## Setup GitHub Pages
GitHub Pages allows users to host websites based on their GitHub repositories for free.

1. Firstly, you will need a **GitHub account** (a free account works fine).
2. To manage your work, download either [Git](https://git-scm.com/) or [GitHub Desktop](https://desktop.github.com/) and link this to your GitHub account.
3. Building a very basic webpage is quite straight forward once you've done the previous 2 steps. Follow [this GitHub Pages link](https://pages.github.com/) that shows step-by-step how to create a very basic webpage.
4. **Optional:** If you already own a domain name, you could easily use the custom domain name by creating a file named CNAME containing the URL. I will not go into custom domain names in this tutorial but you can read more about it [here](https://help.github.com/en/github/working-with-github-pages/configuring-a-custom-domain-for-your-github-pages-site)

## Download and Install Jekyll
Jekyll is a static site generator written in Ruby, and it is the engine behind GitHub Pages.
1. Download and install a Ruby development environment.
  * I got the RubyInstaller for Windows following [this guide](https://jekyllrb.com/docs/installation/windows/).
  * Here are the [installation instructions](https://jekyllrb.com/docs/installation/#requirements) for other operating systems.
2. Check in command line that Ruby and Gem are both installed. If correctly installed, these commands should tell you the version details:
```bash
ruby -v
gem -v
```
3. In command line, install Jekyll and bundler gems, then check that Jekyll is installed:
```bash
gem install jekyll bundler
jekyl -v
```

## Creating a Jekyll website
Alright, now that you have Jekyll installed you're ready to create a website!
1. In command line, navigate to an appropriate folder, then type out:
```bash
jekyll new my_website_name
```
  * A bunch of files will be created inside the new folder, which are necessary to build a basic website.
  * This [video](https://youtu.be/pxua_1vyFck) explains the role of each file.
2. In command line, navigate into the new directory you just made:
```bash
cd my_website_name
```
3. In command line, build the site and make it available on a local web server:
```bash
bundle exec jekyll serve
```
4. You can view the website on [http://localhost:4000](http://localhost:4000).

## Getting a (pre-made) theme
Many Jekyll themes are available and you can also create your own, as documented [here](https://jekyllrb.com/docs/themes/). To get started, let's pick a pre-made theme.
1. After browsing and finding a theme that you like, you can fork or download the theme package. Usually the particular theme will contain instructions for this.
2. In command line, navigate to the folder of the theme you downloaded and run:
```bash
gem install bundler
```
Then:
```bash
bundle install
```
3. Examine the `_config.yml` file and if appropriate, you can modify some options such as `baseurl:""` and Google Analytics code, etc.
4. To get a quick view of what the website looks like in your local web server, type in command line:
```bash
bundle exec jekyll serve
```

## Creating posts and pages
Writing posts and editing pages are relatively straight forward and you can begin to experiment by modifying the templates that the themes came with.

## Working with draft posts
1.	Make a `_drafts` folder inside your Jekyll website folder.
2.	Write your draft in a new `.md` file saved inside this `_drafts` folder.
3.	The draft will not be displayed or rendered on your website.
4.	Thus, to see how the drafts would look like on your website, enter into command line:
```bash
jekyll serve --draft
```
-	Jekyll serve –draft
5.	Now the draft should show up when you browse on the local web server.

## Hosting main Jekyll website on username.github.io
1.	Make a repository called `username.github.io`, where 'username' is your GitHub username.
2.	Clone this repository to your local device.
3.	On local device, copy everything from the Jekyll website folder into this repository.
4.	Commit the changes.
  * From experience, it worked fine if you commit to the master branch.
5.	Push to origin.
6.	Give it a few seconds, then your website should become live on http://username.github.io/.

## Hosting a project Jekyll website on username.github.io/project_name
This is very similar to hosting the main website but with a few modifications.
1.	Make a repository called `project_name`, where 'project_name' is the name of your project.
2.	Clone this repository to your local device.
3.	On local device, copy everything from the Jekyll website folder into this repository.
4.	Inside the `_config.yml` file, change `baseurl` from `""` to `"/project_name"`.
5.	Commit changes.
  * From experience, it worked fine if you commit to the master branch.
  * You could also commit to a new branch named exactly as `gh-pages`. If you do this, GitHub will recognise automatically that it is for a website and you can skip step 7 below.
6.	Push to origin.
7.	Inside the **Settings** tab of your project_name repository on github.com, scroll down to the **GitHub Pages** section and make sure that the **Source** is set to master branch.
8.	Give it a few seconds, then your project website should become live on http://username.github.io/project_name/.

## The end
That's it for this quick, condensed tutorial on building your own website on GitHub Pages using Jekyll! It took me about a day to do all these steps. However, it definitely could have been quicker, as I was not familiar with GitHub in the beginning and had no prior knowledge about building websites.

I have only covered the basic about GitHub Pages and Jekyll here, but as you keep experimenting you'll see that it is quite powerful and it is amazing that this is all available for free! :)


<script data-ad-client="ca-pub-2169940957445604" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
