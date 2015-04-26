---
layout: article
title: "02 - How to Make Posts in Jekyll."
modified:
categories: programming
subcategories: tips
excerpt:
tags: []
image:
  feature:
  teaser: jekyll.png
  thumb:
date: 2015-04-12T14:55:42+02:00
---

Ok, so this is a selfish post, but I have been struggling to get these posts looking good, so I'm leaving this here for later reference.  This post is just for me to learn a bit about octopress and some formatting stuff so if you're an outsider, sorry for the clutter!  This probably won't be very interesting.

To spin up a local server navigate to the local repository folder and type

{% highlight bash %}
bundle exec jekyll serve --watch
{% endhighlight %}

To generate a post under some heading, open a terminal and navigate to the site folder.  Then, run the following code:

<code>bundle exec octopress new post "NAME_OF_POST" --dir path/to/post </code>

This will generate a markdown file at the appropriate point in the file tree.  Jekyll should automatically update the parent page to add a link to the post.

If you would like to create a new page, the syntax is similar:

<code>bundle exec octopress new page path/to/page</code>

However, jekyll will not automatically create the required links, so you'll have to do this yourself.


Formatting Junk
----------------
<pre><code>Type</code></pre>

{%highlight bash %}
some code
{% endhighlight %}

{%highlight python linenos %}
import numpy
print("foobar")
{% endhighlight %}

HUZZZAAHHHH! The above code took a long time to find, so here's how it goes in markdown:
{%highlight liquid linenos %}
{{ "{%highlight python linenos "}}%} 
import numpy
print("foobar")
{{ "{% endhighlight "}} %}
{% endhighlight %}




To add headlines, type
{%highlight html linenos %}
HEADLINE
--------
{% endhighlight %}

You can add hash tags to the front to change the size of the header.

If you want a link that opens in a new tab use

{% highlight html linenos %}
<a href="www.website.com" target="_blank">Link Text</a>
{% endhighlight %}


