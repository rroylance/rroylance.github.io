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

-  Clone repo located at <repo> onto local machine. Original repo can be located on the local filesystem or on a remote machine via HTTP or SSH.
{% highlight %}
    git clone <repo>
{% endhighlight %}

-  Define author name to be used for all commits in current repo. Devs commonly use --global flag to set config options for current user.
{% highlight %}
    git config user.name <name>
{% endhighlight %}

-  Stage all changes in <directory> for the next commit. Replace <directory> with a <file> to change a specific file.
{% highlight %}
    git add <directory>
{% endhighlight %}

-  Commit the staged snapshot, but instead of launching a text editor, use <message> as the commit message.
{% highlight %}
    git commit -m "<message>"
{% endhighlight %}

-  List which files are staged, unstaged, and untracked.
{% highlight %}
    git status
{% endhighlight %}

-  Display the entire commit history using the default format. For customization see additional options.
{% highlight %}
    git log
{% endhighlight %}

-  Show unstaged changes between your index and working directory.
{% highlight %}
    git diff
{% endhighlight %}

##### Undoing Changes

-  Create new commit that undoes all of the changes made in <commit>, then apply it to the current branch.
{% highlight %}
    git revert <commit>
{% endhighlight %}

-  Remove <file> from the staging area, but leave the working directory unchanged. This unstages a file without overwriting any changes.
{% highlight %}
    git reset <file>
{% endhighlight %}

-  Shows which files would be removed from working directory. Use the -f flag in place of the -n flag to execute the clean.
{% highlight %}
    git clean -n
{% endhighlight %}

##### Rewriting History

-  Replace the last commit with the staged changes and last commit combined. Use with nothing staged to edit the last commit’s message.
{% highlight %}
    git commit --amend
{% endhighlight %}

-  Rebase the current branch onto <base>. <base> can be a commit ID, a branch name, a tag, or a relative reference to HEAD.
{% highlight %}
    git rebase <base>
{% endhighlight %}

-  Show a log of changes to the local repository’s HEAD. Add --relative-date flag to show date info or --all to show all refs.
{% highlight %}
    git reflog
{% endhighlight %}

##### Branches

-  List all of the branches in your repo. Add a <branch> argument to create a new branch with the name <branch>.
{% highlight %}
    git branch
{% endhighlight %}

-  Create and check out a new branch named <branch>. Drop the -b flag to checkout an existing branch.
{% highlight %}
    git checkout -b
<branch>
{% endhighlight %}

-  Merge <branch> into the current branch.
{% highlight %}
    git merge <branch>
{% endhighlight %}

##### Remote Repositories

-  Create a new connection to a remote repo. After adding a remote, you can use <name> as a shortcut for <url> in other commands.
{% highlight %}
    git remote add <name> <url>
{% endhighlight %}

-  Fetches a specific <branch>, from the repo. Leave off <branch> to fetch all remote refs.
{% highlight %}
    git fetch <remote> <branch>
{% endhighlight %}

-  Fetch the specified remote’s copy of current branch and immediately merge it into the local copy
{% highlight %}
    git pull <remote>
{% endhighlight %}

-  Push the branch to <remote>, along with necessary commits and objects. Creates named branch in the remote repo if it doesn’t exist.
{% highlight %}
    git push <remote> <branch>
{% endhighlight %}

##### Config

-  Define the author name to be used for all commits by the current user
{% highlight %}
    git config --global user.name <name>
{% endhighlight %}

-  Define the author email to be used for all commits by the current user
{% highlight %}
    git config --global user.email <email>
{% endhighlight %}

-  Create shortcut for a Git command. E.g. alias.glog log --graph --oneline will set git glog equivalent to git log --graph --oneline.
{% highlight %}
    git config --global alias. <alias-name> <git-command>
{% endhighlight %}

-  Set text editor used by commands for all users on the machine. <editor> arg should be the command that launches the desired editor (e.g., vi).
{% highlight %}
    git config --system core.editor <editor>
{% endhighlight %}

-  Open the global configuration file in a text editor for manual editing.
{% highlight %}
    git config --global --edit
{% endhighlight %}

##### Log

-  Limit number of commits by <limit>. E.g. git log -5 will limit to 5 commits
{% highlight %}
    git log -<limit>
{% endhighlight %}

-  Condense each commit to a single line.
{% highlight %}
    git log --oneline
{% endhighlight %}

-  Display the full diff of each commit.
{% highlight %}
    git log -p
{% endhighlight %}

-  Include which files were altered and the relative number of lines that were added or deleted from each of them.
{% highlight %}
    git log --stat
{% endhighlight %}

-  Search for commits by a particular author.
{% highlight %}
    git log --author= ”<pattern>”
{% endhighlight %}

-  Search for commits with a commit message that matches <pattern>.
{% highlight %}
    git log --grep=”<pattern>”
{% endhighlight %}

-  Show commits that occur between <since> and <until>. Args can be a commit ID, branch name, HEAD, or any other kind of revision reference.
{% highlight %}
    git log <since>..<until>
{% endhighlight %}

-  Only display commits that have the specified file.
{% highlight %}
    git log -- <file>
{% endhighlight %}

-  --graph flag draws a text based graph of commits on left side of commit msgs. --decorate adds names of branches or tags of commits shown.
{% highlight %}
    git log --graph --decorate
{% endhighlight %}

##### Diff

-  Show difference between working directory and last commit.
{% highlight %}
    git diff HEAD
{% endhighlight %}

-  Show difference between staged changes and last commit
{% highlight %}
    git diff --cached
{% endhighlight %}

##### Reset

-  Reset staging area to match most recent commit, but leave the working directory unchanged.
{% highlight %}
    git reset
{% endhighlight %}

-  Reset staging area and working directory to match most recent commit and overwrites all changes in the working directory.
{% highlight %}
    git reset --hard
{% endhighlight %}

-  Move the current branch tip backward to <commit>, reset the staging area to match, but leave the working directory alone.
{% highlight %}
    git reset <commit>
{% endhighlight %}

-  Same as previous, but resets both the staging area & working directory to match. Deletes uncommitted changes, and all commits after <commit>.
{% highlight %}
    git reset --hard <commit>
{% endhighlight %}

##### Rebase

-  Interactively rebase current branch onto <base>. Launches editor to enter commands for how each commit will be transferred to the new base.
{% highlight %}
    git rebase -i <base>
{% endhighlight %}

##### Pull

-  Fetch the remote’s copy of current branch and rebases it into the local copy. Uses git rebase instead of merge to integrate the branches.
{% highlight %}
    git pull --rebase <remote>
{% endhighlight %}

##### Push

-  Forces the git push even if it results in a non-fast-forward merge. Do not use the --force flag unless you’re absolutely sure you know what you’re doing.
{% highlight %}
    git push <remote> --force
{% endhighlight %}

-  Push all of your local branches to the specified remote
{% highlight %}
    git push <remote> --all
{% endhighlight %}

-  Tags aren’t automatically pushed when you push a branch or use the --all flag. The --tags flag sends all of your local tags to the remote repo
{% highlight %}
    git push <remote> --tags
{% endhighlight %}

##### Tags

-  List the local repository's tags.
{% highlight %}
    git tag
{% endhighlight %}

-  List the local repository's tags that match a pattern. Use a * as a wildcard.
{% highlight %}
    git tag -l <pattern>
{% endhighlight %}

-  Creates a lightweight tag named <example> as a reference in .git/refs/tags/<example>, which points to the current commit. 
{% highlight %}
    git tag <example>
{% endhighlight %}

-  Creates an (unsigned) annotated tag named <example> as a reference in .git/refs/tags/<example> with the attached message <message>, which points to the current commit. 
{% highlight %}
    git tag -a <example> -m <message>
{% endhighlight %}

-  Delete all tags in a repo on origin.
{% highlight %}
    git tag -l | xargs -n 1 git push --delete origin
{% endhighlight %}

-  Delete all tags in a repo locally.
{% highlight %}
    git tag | xargs git tag -d
{% endhighlight %}

###### Thanks Atlassian for many of these, from their awesome [Cheat Sheet](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)
