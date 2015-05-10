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

<div class="notice-info">
    <h5>Watch out!</h5> Don't make the same mistake as I did and install the webupd8 version.  You will not have the correct path and installing package will not work properly.  Follow these steps for Ubuntu.
</div>

If you are using Ubuntu, life used to be terrible and you would have to build Atom from scratch.  However, you can now download the debian version and install Atom in a snap.  To install atom, first download the debian file from the <a href="http://atom.io" target="blank"><strong>Atom home page</strong></a>.  Then simply pop open a terminal (by typing `ctrl + alt + t`) and then type the following

{% highlight bash %}
cd Downloads
sudo dpkg --install atom-amd64.deb
{% endhighlight %}

That's it! Atom is installed and you can start programming! So easy.

Using Atom
---------------
Now that you have Atom installed, what features of Atom are most useful for Python programming, R, etc.?  Well, I installed Atom this morning to write this post and I am already in love with it.  Seriously, I have been using it for an hour and this is what my screen looks like:

![atom_screen_1](http://tyler-abbot.github.io/images/atom_screen_1.png)

I can edit in multiple languages in different panes, there is a file tree that I can use to navigate to new files, and the default color-scheme and syntax highlighting are great.  That being said, the fact that Atom is open source and modular means that there are a ton of cool packages you can download.  I'm going to try some out and describe them here, but there are many more so have fun and get your set-up just how you want it!

Sweet Packages
-----------
First of all, one of the great things about Atom is its ease of use.  You can type <code>cntrl+shift+p</code> to get a search bar, from which you can simply search for the packages you want, or settings or whatever else you are interested in.

* <a href="https://github.com/AtomLinter/Linter" target="blank"><strong>Linter.</strong></a>  This package is a great idea, indicating errors inline, while you type.  You can install different packages for different languages.  However, I'm personally having some troubles with the <code>$PATH</code> variable, so I'll update this if I can ever get it working.  <strong>UPDATE:</strong> In Ubuntu, you need to install flake8, not only as a package, but as an executable.  Run the following in the terminal then use the output to update the executable dir in the settings of linter-flake8 in Atom.  That should do it!

{% highlight bash %}
sudo apt-get install python-flake8
which flake8
{% endhighlight %}



* <a href="https://atom.io/packages/ask-stack" target="blank"><strong>Ask-stack.</strong></a> Oh. My. Goodness.  This package will make your life wonderful if you are new to programming.  It allows you to seach Stack Exchange for answers to questions directly in Atom.  Personally, when I first started using Python I spent half my time on Stack Exchange trying to figure out how to do things.  I haven't used this package much, so I don't know much about its interface, but I'm sure I'll be using it in the future.

Conclusion
-------------------
I hope you enjoy Atom, but if you want to be a cool kid and suffer through years of learning a new program, go check out Vim, Emacs, or any of the other text editors out there.  Overall, it's probably best to at least be able to talk shop about them and lament your struggles with people... although that makes it sound like my social circle is pretty limited...
