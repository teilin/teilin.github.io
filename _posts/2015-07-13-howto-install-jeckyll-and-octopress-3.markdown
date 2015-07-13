---
layout: post
title: "Howto Install Jekyll and Octopress 3"
date: 2015-07-13T20:57:56+02:00
---

I have been using [Octopress]() a while back, but for some reason I stoped using it. It was because I thought the [Ghost]() blog engine would be what I always wanted. Then I started reading about Octopress 3 and some collegeas at work told me how good that one is.

Maybe the biggest upside for me choosing Octopress is because it is a static site. Which means that I can use my Github account to host the blog for free.

I started looking around to see if anyone had a nice walkthrough how to setup Octopress 3 and I found [chrisanthropic.com: Installing Octopress 3.0 From Scratch](http://www.chrisanthropic.com/blog/2014/installing-octopress-3-0-from-scratch/). That looked like what I was looking for. After a while, it was clear to me that this guild was a little bit outdated, so here are the steps I did.

#Install Octopress
	gem install octopress
	gem install bundler
	octopress new <yourblogname>
	cd <yourblogname>
	
#Create a git repository
	git init
	
Create a repository at Github where you want to publish your blog. Then you need to add some lines to your .gitignore file.

	_deploy.yml
	.bundle
	bin
	vendor
	
#Build your blog
The part I used some time to find out was how I was suppose to build the blog. Everywhere I looked different blogs included the guide I followed had the command `octopress build`. By looking at the subcommand to octopress, there are no build command. Then it got to me that it probably is Jekyl that should be used to build the blog.

	jekyll build
	
#Deploy your blog
	octopress deploy init <git@github.com:teilin/teilin.github.io.git>
	
Using the `octopress deploy init` command, the _deploy.yml file is generated. I did not do any changes in this file at all.

Running `octopress deploy` now, will deploy your site to your Github pages.