---
layout: article
title: "04 - Text Editors"
modified:
categories: programming
subcategories: tips
excerpt:
tags: []
image:
  feature:
  teaser:
  thumb:
date: 2015-05-10T10:20:57+02:00
---

{% include toc.html %}

This post is meant to help you get started programming as quickly as possible and, if you are already familiar with text editors, is pretty one sided.  We are going to talk about how to install and use <a href="https://www.atom.io" target="blank"><strong>Atom</strong></a>, the open-source text editor from GitHub.

Why This Post Is So One Sided
----------------------
When I first started programming (at least in the recent past) I did so in Python and wanted to do the cool things that the cool programmers were doing, so I jumped straight in with <a href="https://www.vim.org" target="blank"><strong>Vim</strong></a>.  If you ask any professional Unix programmer, there are only two text editors, Vim and Emacs, but these two programs are like the great pyramids.  They are incredibly powerful and useful for those who know how to use them, but for others they are like learning to read hyroglyphs.  For example, the first time I set up Vim I spent an entire day just trying to find and edit my vimrc file to change the colorscheme, because if you know where it is then no problem, but if you don't then you are lost and no one else seems to have the same problem!!!  Oh, and add the fact that keyboard shortcuts are completely different from standards, like "copy" is "y" for "yank".

That little rant over, this post is about how to get started quickly with a versatile, cheap, and nice text editor.  Atom is all of these.  GitHub developed Atom as a free, open source text editor with their own development needs in mind.  Apparently Atom is very similar to another editor, <a href="https://www.sublimetext.com" target="blank"><strong>Sublime</strong></a>, but Atom has near weekly new releases and is free, compared to yearly releases and a $70 price tag.  So, we'll see how easy Atom is to install and set-up, then we'll talk a little about other options... maybe.

If you're interested in some reviews or comparisons, check out these links:

* <a href="http://blog.takipi.com/sublime-vs-atom-text-editor-battles/" target="blank"><strong>Sublime v. Atom</strong></a>
* <a href="http://en.wikipedia.org/wiki/Comparison_of_text_editors" target="blank"><strong>All text editors ever, forever... seriously.</strong></a>
* <a href="http://lifehacker.com/five-best-text-editors-1564907215" target="blank"><strong>Comparing the "top 5".</strong></a>

Installing Atom
----------------
The first thing you should do is head over to the <a href="https://atom.io/docs" target="blank"><strong>Atom Documentation.</strong></a>  You can follow the "Getting Started" link, where you'll learn about Atom and then how to install Atom on Apple, Windows, Debian, or Redhat, all in about 5 minutes.

If you are using Ubuntu, life used to be terrible and you would have to build Atom from scratch.  However, <a href="http://www.webupd8.org/2014/05/install-atom-text-editor-in-ubuntu-via-ppa.html" target="blank"><strong>Andrew at webupd8.org has created a repository so you can install Atom super fast!</strong></a>  To install atom, simply pop open a terminal (by typing `ctrl + alt + t`) and then type the following

{% highlight bash %}
sudo add-apt-repository ppa:webupd8team/atom
sudo apt-get update
sudo apt-get install atom
{% endhighlight %}

That's it! Atom is installed and you can start programming! So easy.

Using Atom
---------------
Now that you have Atom installed, what features of Atom are most useful for Python programming, R, etc.?  

![atom_screen_1](http://tyler-abbot.github.io/images/atom_screen_1.png)
