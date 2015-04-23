---
layout: article
title: "Some TeX Tips."
modified:
categories: programming
subcategories: tex
excerpt:
tags: []
image:
  feature:
  teaser:
  thumb:
date: 2015-04-12T14:52:06+02:00
---

For later reference when I actually write this post:

When you want to add new packages, you should store them in

{% highlight bash linenos %}
/usr/local/texlive/texmf-local/tex/latex/tmabbot
{% endhighlight %}

or without linenumbers

{% highlight bash %}
/usr/local/texlive/texmf-local/tex/latex/tmabbot
{% endhighlight %}

Then, you need to run <code>texhash</code> by typeing

{% highlight bash %}
sudo /opt/texbin/texhash
{% endhighlight %}

