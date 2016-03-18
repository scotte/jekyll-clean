---
layout: post
title: "Using Github and jekyll to build your personal blog like this"
category: [Others]
tag: [Github, jekyll]
date: 2016-03-17 15:00:00
comments: true
---



References:
1.http://beiyuu.com/github-pages/
2.https://davidburela.wordpress.com/2015/11/28/easily-install-jekyll-on-windows-with-3-command-prompt-entries-and-chocolatey/
3.https://ruby-china.org/topics/29250
4.
Step by step:
1. Install Jekyll on Windows
	1.1 Chocolatey
		Open a command prompt with Administrator access
		Install Chocolatey with the following code
			@powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin
		Close the command prompt as Chocolatey will not be available until you close and reopen
	1.2 Install dependencies & Jekyll
		choco install ruby -y
		reopen command prompt with Administrator access
		gem sources --add http://gems.ruby-china.org/ --remove https://rubygems.org/
		gem install jekyll
	1.3 some dependencies
		download and install DevKit (refers to https://github.com/oneclick/rubyinstaller/wiki/Development-Kit)
		gem install wdm jekyll-paginate
2. Get a bolg follow the jekyll
	fork a jekyll theme such as https://github.com/streetturtle/jekyll-clean-dark
	rename the repository
	git clone to local folder
	cd to this folder
	jekyll serve --baseurl=''
	then you can browse to http://127.0.0.1:4000/
3. Using jekyll at Github
	https://help.github.com/articles/setting-up-your-pages-site-locally-with-jekyll/
	gem install bundle
	gem install github-pages
	bundle exec jekyll serve
	