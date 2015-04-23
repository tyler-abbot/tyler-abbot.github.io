---
layout: article
title: "How to Make Posts."
modified:
categories: programming
subcategories: tips
excerpt:
tags: []
image:
  feature:
  teaser:
  thumb:
date: 2015-04-12T14:55:42+02:00
---

This post is just for me to learn a bit about octopress and some formatting stuff.  It will act as a reference for creating posts later, so if you're an outsider, sorry for the clutter!  This probably won't be very interesting.

To generate a post under some heading, open a terminal and navigate to the site folder.  Then, run the following code:

<code>bundle exec octopress new post "NAME_OF_POST" --dir path/to/post </code>

This will generate a markdown file at the appropriate point in the file tree.  Jekyll should automatically update the parent page to add a link to the post.

If you would like to create a new page, the syntax is similar:

<code>bundle exec octopress new page path/to/page</code>

However, jekyll will not automatically create the required links, so you'll have to do this yourself.


(All this stuff below is just for later reference)
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


<div class="highlightable">
    <p>print 'bar'</p>
</div>

<table class="highlighttable"><tr><td class="linenos"><div class="linenodiv"><pre><code class="language-css" data-lang="css">1
2
3
4
5</code></pre></div></td><td class="code"><div class="highlight"><pre><span class="nf">#container</span> <span class="p">{</span>
	<span class="k">float</span><span class="o">:</span> <span class="k">left</span><span class="p">;</span>  
	<span class="k">margin</span><span class="o">:</span> <span class="m">0</span> <span class="m">-240px</span> <span class="m">0</span> <span class="m">0</span><span class="p">;</span>  
	<span class="k">width</span><span class="o">:</span> <span class="m">100%</span><span class="p">;</span>
<span class="p">}</span>
</pre></div>
</td></tr></table>


To add headlines, type
{%highlight html linenos %}
HEADLINE
--------
{% endhighlight %}

You can add hash tags to the front to change the size of the header.
