---
layout: article
title: "01 - Why Python? I Already Know R!"
modified:
categories: programming
subcategories: python
excerpt:
tags: []
image:
  feature:
  teaser:
  thumb:
date: 2015-04-16T18:13:19+02:00
---
{% include toc.html %}

Introduction
-------------
Python and R are both widely used in the sciences and social sciences, but the two tend to be used by different user groups.

R was developed by statisticians for statisticians.  Originally developed by Ross Ihaka and Robert Gentleman at the University of Auckland, New Zealand, in 1993, the language has taken the statistical field by storm.  Actually, you can't quite call R a language... unlike Python, R is a software environment geared specifically towards statistics.  That means that R is similar to Matlab or Stata, but OpenSource.  It's not clear from the 20 minutes I spent trying to figure out how R works exactly what the program does, but as far as I can tell R is a highlevel language interpreter similar to Python.

Python was developed by computer programmers for everyone.  In the late 1980's, Guido van Rossum developed an interpreter and language as a hobby (!) and since then the "core philosophy" of python has become the "zen of Python" (just open up ipython and type <code>import this</code>).  The overall thrust is to make the programming experience as easy as possible.  Essentially, when you execute Python code, the program is parsed, compiled, and interpreted.  Compared to a language like C++, the process is similar, but you don't actually have to carry out the steps yourself in Python!


What are the differences between R and Python?
-----------------------
There are several key differences between R and Python, including versatility, available packages, and usability.

One of the biggest benefits and downfalls for R is its precise focus on statistics.  If there is a cutting edge statistical method, from econometrics to biometrics, it is surely available as an R package.  However, the development of the project let fall some of the freedom one needs to deal with big-data.  As is described in [this](https://blogs.oracle.com/R/entry/what_is_r) article, R is only single thread and can create duplicate data objects that quickly overload the onboard memory.  Because of this, R becomes unsuitable for big-data applications or massive computation.  This is where Python really shines, through packages like [PyCuda](http://documen.tician.de/pycuda/), [PyPy](http://pypy.org/), and [StarCluster](http://star.mit.edu/cluster/), that allow you to create massively parallel programs and run them easily on cloud computing services.

Python truly falls short in terms of statistical analysis packages, but this seems to be changing.  R benefits from its specialty purpose, in that EVERY SINGLE PACKAGE created for R is used for statistics.  On the other hand, the number of contributors to Python is far greater than that for R, but the number of statisticians is much smaller.  However, that number is beginning to reach a critical mass such that statistical modules in Python must compete and are becoming better.  Alongside the traditional [Pandas](http://pandas.pydata.org/) package, you now have new things like [Statsmodels](http://statsmodels.sourceforge.net/stable/) that have many of the tools you might be looking for.

Finally, if you are just starting out with programming, Python may seem too daunting.  It is true that with tools like [RStudio](http://www.rstudio.com/) you can work with R in a MatLab like graphical user interface that is easy and intuitive.  On the flipside, installing and learning to leverage Python involves downloading and installing text editors and setting path variables, etc. that may seem daunting to a newbie.  However, new tools like [Lighttable](http://lighttable.com/) are making the whole process more palatable.


Which should I choose?
----------------

You're not going to like this... but you should learn BOTH!  If you don't already know a program like R or Python, then that means you are either a student or someone changing careers.  You are not mired in the tradition of R or too much of a programming wunderkind to shy-away from the one trick pony of R.  That being said, everyone you work with will know one or the other and if you want to be able to move from project to project with ease you need to know both.

Personally, I am only familiar with academia.  Every professor will only know Matlab and (maybe) R, so in order to work with them it is necessary to be familiar.  But, the most cutting edge tools are in Python and large scale computation is heavy and slow in R, so in order to be able to compete in the future I see Python (or C++) as a necessity.

Where are things heading?
---------------

Neither one of these languages is going anywhere soon.  That being said, I think that the number of passionate programmers and statisticians working on Python is growing in comparison to R and that in the future we'll need more versatile tools.

