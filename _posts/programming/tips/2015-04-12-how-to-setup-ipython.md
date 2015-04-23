---
layout: article
title: "How to Setup Ipython."
modified:
categories: programming
subcategories: tips
excerpt:
tags: []
image:
  feature:
  teaser: IPy_header.png
  thumb:
date: 2015-04-12T11:56:17+02:00
---
{% include toc.html %}

If you are hoping to get into Python and need help getting set-up, this post is for you.  My preference for installing Python is Continuum Analytics' Anaconda bundle.  It comes with all the packages you need to get started and is quick and easy to install.  I'll go through the steps for getting up and running quickly in Ubuntu Linux, as well as covering some of the most useful features of Ipython.  If you are using OS or Windows the steps are a little different and you can find a guide <a href="https://store.continuum.io/static/img/Anaconda-Quickstart.pdf" target="_blank">HERE.</a>

Installation
------------

First, you'll need to download Anaconda <a href="https://store.continuum.io/cshop/anaconda/" target="_blank">HERE.</a>  The site will detect your system and suggest the proper insall.  NOTE: If you are running a 32-bit operating system, you will have problems in the future if you want to install more advanced tools like PyCuda (I had to reinstall my entire operating system).  Also, I suggest you go with a Python 2.X version.  Although Python 3.X is available, some packages do not have good backwards compatibility.

Second, open up a terminal and navigate to your Dowloads folder by typing

{%highlight bash %}
cd Downloads/
{% endhighlight %}

Once there, execute the installer by typing in the terminal

{%highlight bash %}
bash NAME_OF_FILE
{% endhighlight %}

where you replace NAME_OF_FILE with the name of your download, which changes with version.  You'll be prompted to specify an install location.  Use the default so that you can easily find what you are looking for later.


Setup
--------
Next, you need to add the anaconda file to your path variable, so that terminal can find it.  As a side note, you can learn more about what PATH is and why it always seems to be a problem <a href="http://www.linfo.org/path_env_var.html" target="_blank">HERE.</a>  To see what the path variable is type the following in the terminal

{%highlight bash %}
echo $PATH
{% endhighlight %}

If you do not see a folder containing the word "anaconda", you need to update the PATH.  Type the following into the terminal

{%highlight bash %}
export PATH=/path/to/anaconda:$PATH
{% endhighlight %}

Which will append the directory to your path.  My anaconda directory is under <code>/home/user_name/anaconda/bin</code>, but yours might be slightly different.

Now open a new terminal window and type <code>ipython</code>.  That's it!  You're now using Python!

Python-ing!
-----------
Now that you have your sweet Ipython set-up, what can it do?!  There are several ways to work with Ipython.  First, you can work directly at the command line.  By typing <code>ipython</code> at the terminal you open an "Ipython shell", where whatever you type will run in Python.  Another way to work on more complex projects is to write Python programs in a text-editor, such as Vim or Lightbox (post to come), and then to run these programs in your Ipython shell.  Finally, one of the coolest things you can do is to use the Ipython Notebook.  Open up a terminal and type

{%highlight python %}
ipython notebook
{% endhighlight %}

This will open up an Ipython Notebook session in your default browser.  Then you can create a new ipython notebook, like <a href="http://nbviewer.ipython.org/github/tyler-abbot/tyler-abbot.github.io/tree/master/misc/test.ipynb" target="_blank">this one</a>.  Ipython notebooks are great teaching tools, so I'll be using them often on this site to describe lots of things.

That's it!  You are now ready to learn to program in Python.  For more on different packages, best-practices (as far as an economist knows best practices), and lots of other stuff about Python, head <a href="{{ site.url }}/programming/python.html" target="_blank">here</a>. 

