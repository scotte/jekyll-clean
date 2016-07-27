---
layout: post
title: "Jekyll Clean Theme"
date: 2014-08-22 16:25:06 -0700
comments: false
---

* Get it from [github](https://github.com/scotte/jekyll-clean).
* See the [live demo](https://scotte.github.io/jekyll-clean).
* See it [in action on my own blog](https://scotte.org).

Welcome to the sample post for the Jekyll Clean theme.

A simple and clean Jekyll theme using [bootstrap](http://getbootstrap.com)
(not to be confused with jekyll-bootstrap) that's easy to modify and very
modular in component and element reuse.

It uses Disqus for comments and includes Google Analytics support. Both of
these features are disabled by default and can be enabled via \_config.yml. You
can also rip this code out of the templates if you like (footer.html and post.html).
The beauty of Jekyll - keep things clean... Jekyll Clean!

The theme works well on mobile phones, using a collapsable nav bar and hiding the
sidebar. The links pane in the sidebar is available on mobile through the nav menu,
and you can do the same thing for any other sections added to the sidebar.

Don't forget to occassionally merge against my upstream repository so you can get
the latest changes. Pull requests are encouraged and accepted!

Installation
============

If you don't have a blog already on github, start by cloning this repository.
Best to do that directly on github and then clone that down to your computer.

If you already do have a blog, You can certainly apply this theme to your existing
blog in place, but then you won't be able to merge as the theme changes. If you
re-apply your blog history on top of this theme's **gh-pages** branch, it's then
easy to update to the latest version of the theme. You also don't want to have to
deal with resolving old conflicts from your existing history, so you may wish to to
push your existing master off to a new branch so you have the old history and start
a new branch with this as the start, merging in your \_posts and other assets (after
git rm'ing the current \_posts.

Not ideal, but you have to make a choice - either apply it manually or base your
blog off this theme's branch. Either way it will work, and both have their own
pros and cons.

You can setup an upstream tracking repository like so:

```
$ git remote add upstream git@github.com:scotte/jekyll-clean.git
```
And now when you wish to merge your own branch onto the latest version of the
theme, simply do:

```
$ git fetch upstream
$ git merge upstream/gh-pages
```

Of course you will have to resolve conflicts for \_config.yml, \_includes/links-list.html,
and \_posts, and so on, but in practice this is pretty simple.

This is how I maintain my own blog which is based on this theme. The old history is
sitting in an **old-master** branch that I can refer to when I need to.

Running Locally
===============

Here's the exact set of packages I need to install on Debian to run jekyll
locally with this theme for testing.

```
$ sudo aptitude install ruby ruby-dev rubygems nodejs
$ sudo gem install jekyll jekyll-paginate
```

And then it's just a simple matter of running jekyll locally:

```
$ jekyll serve --baseurl=''
```

Now browse to http://127.0.0.1:4000

Using gh-pages
==============

Running a jekyll site is a bit outside the scope of this doc, but
sometimes it can be a bit confusing how to configure jekyll for
project pages versus user pages, for example.

To start with, read through
[the documentation here](https://help.github.com/articles/user-organization-and-project-pages/).
This will provide a good overview on how it all works. The git branch and
baseurl (in _config.yml) will change depending on the sort of site deployed.

When you clone this repository, it's set up for project pages, so the
deployed branch is "gh-pages" and baseurl is configured to 'jekyll-clean',
because that's the name of this project.

If you plan to deploy this as user pages, the deployed branch is "master"
and baseurl is configured to '' (i.e. empty).

Comment Systems
===============

Jekyll clean supports both [isso](https://posativ.org/isso) and
[disqus](https://disqus.com) comment systems.

After enabling **comments**, either **isso** or **disquss** must
be configured. Don't try configuring both!

Isso Comments
=============

Isso requires running a local server, so is not suitable for hosting
in github pages, for example. Isso is open source and keeps all your
data local, unlike Disqus (who knows exactly what they are doing with
your data).

In _config.yml you'll need to set **isso** to the fully-qualified URL
if your isso server (this is the value for **data-isso** passed to the
isso JS). Make sure **comments** is true.


Disqus Comments
===============

Getting Disqus to work can be a bit more work than it seems like it should be.
Make sure your Disqus account is correctly configured with the right domain
of your blog and you know your Disqus shortname.

In _config.yml you'll need to set **disqus** to your Disqus shortname and
make sure **comments** is true.

Finally, in posts, make sure you have **comments: true** in the YAML front
matter.

More information on using Disqus with Jekyll is
[documented here](https://help.disqus.com/customer/portal/articles/472138-jekyll-installation-instructions).

Code Syntax Highlighting
========================

To use code syntax highlighting, use the following syntax:

```
```python
import random

# Roll the die
roll = random.randint(1, 20)
print('You rolled a %d.' % roll)
``` #REMOVE
```

(Remove #REMOVE from the end of the last line). Which will look like this in
the rendered jekyll output using the default css/syntax.css provided with this
theme (which is the **colorful** theme from [https://github.com/iwootten/jekyll-syntax](https://github.com/iwootten/jekyll-syntax)):

```python
import random

# Roll the die
roll = random.randint(1, 20)
print('You rolled a %d.' % roll)
```

You can, of course, use any theme you wish, see the jekyll and pygments
documentation for more details.

License
=======

The content of this theme is distributed and licensed under a
![License Badge]({{ site.baseurl}}/images/cc_by_88x31.png)
[Creative Commons Attribution 4.0 License](https://creativecommons.org/licenses/by/4.0/legalcode)

    This license lets others distribute, remix, tweak, and build upon your work,
    even commercially, as long as they credit you for the original creation. This
    is the most accommodating of licenses offered. Recommended for maximum
    dissemination and use of licensed materials.

In other words: you can do anything you want with this theme on any site, just please
provide a link to [the original theme on github](https://github.com/scotte/jekyll-clean)
so I get credit for the original design. Beyond that, have at it!

This theme includes the following files which are the properties of their
respective owners:

* js/bootstrap.min.js - [bootstrap](http://getbootstrap.com)
* css/bootstrap.min.css - [bootstrap](http://getbootstrap.com)
* js/jquery.min.js - [jquery](https://jquery.com)
* images/cc_by_88x31.png - [creative commons](https://creativecommons.org)
* css/colorful.css - [iwootten/jekyll-syntax](https://github.com/iwootten/jekyll-syntax)
