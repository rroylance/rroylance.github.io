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

 TBD

#### On to the Tips...

-  To delete all tags in a repo on origin;
{% highlight bash %}
    git tag -l | xargs -n 1 git push --delete origin
{% endhighlight %}

-  To delete all tags in a repo locally;
{% highlight bash %}
    git tag | xargs git tag -d
{% endhighlight %}
