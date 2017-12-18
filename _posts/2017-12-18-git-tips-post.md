---
layout: post
title: "Git Tips & Tricks"
date: 2017-12-18
excerpt: "Some, hopefully, helpful tips & tricks for Git."
tags: [post, tips, tricks, git]
comments: true
---

##### Do you have a tip you'd like added ? Post in the comments below or [send me an email](mailto:roylance.richard+gittips@gmail.com?Subject=Git%20Tip%20Suggestion "EMAIL ME!").

---

#### What is Git?

By far, the most widely used modern version control system in the world today is Git. Git is a mature, actively maintained open source project originally developed in 2005 by Linus Torvalds, the famous creator of the Linux operating system kernel. A staggering number of software projects rely on Git for version control, including commercial projects as well as open source. Developers who have worked with Git are well represented in the pool of available software development talent and it works well on a wide range of operating systems and IDEs (Integrated Development Environments).

Having a distributed architecture, Git is an example of a DVCS (hence Distributed Version Control System). Rather than have only one single place for the full version history of the software as is common in once-popular version control systems like CVS or Subversion (also known as SVN), in Git, every developer's working copy of the code is also a repository that can contain the full history of all changes.

In addition to being distributed, Git has been designed with performance, security and flexibility in mind.

#### On to the Tips...

##### Basics

-  Create empty Git repo in specified directory. Run with no arguments to initialize the current directory as a git repository.
{% highlight %}
    git init <directory>
{% endhighlight %}

###### Thanks Atlassian for many of these, from their awesome [Cheat Sheet](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)
