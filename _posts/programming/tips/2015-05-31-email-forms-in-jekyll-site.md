---
layout: article
title: "05 - Email Forms in Jekyll Site"
modified:
categories: programming
subcategories: tips
excerpt:
tags: []
image:
  feature:
  teaser: ampersand.png
  thumb:
date: 2015-05-31T14:53:20+02:00
---
{% include toc.html %}

<div class="notice">
    <p><h5>Disclaimer:</h5></p>
    <p>This post is incomplete and is left here as a cry for help!  I have struggled for days with this.  If anyone stumbles upon this post and has advice on how to incorporate a contact form into markdown, I would greatly appreciated it...</p>
</div>

I've recently been working on a project to start a non-profit and wanted to build a website.  I used the [Agency theme](http://jekyllthemes.org/themes/agency/){:target="_blank_"}.  You can check out my finished product [here](http://www.allochory.org){:target="_blank_"}.  Although a great theme and really easy to get set-up, I ran into trouble with the e-mail form.  I contacted the theme creator, [Rick Kim](https://github.com/y7kim){:target="_blank_"}, and he imparted some knowledge about static websites that I would like to share with you, as well as aggregate some useful information for adding an e-mail form to a static website.

Why doesn't it work?!
----------------------
So I built this little one page site off the theme in an afternoon and was very proud of myself, but then couldn't get the email form to work.  After spending a day reading about it and stumbling around the internet, I heard back from Rick and he explained something about static websites.  Because a static html website is just a set of files, it can't generate an e-mail from a contact form.  You need to either include a third party contact form or use an e-mail service.  I went with the latter choice, using [SendGrid](https://sendgrid.com){:target="_blank_"}.  What follows is a bit about how I hotwired the standard form to make my e-mail form work.

The original form and a bit about PHP mail()
-------------------------------------
The form in the original Agency theme uses the PHP mail() function.  This function is apparently notorious for being difficult to debug.  A "false" output could be anything from a bad input value to your e-mail DNS being improperly configured.  To add to the problem, the GitHub page cannot even run the function!  Enter a third party.

SendGrid and the new contact form
-----------------------------------
SendGrid is a transactional and marketing email service.  The company was designed by developers to better serve companies e-mail needs.  What we need is their transactional service, which takes on the responsibility of running an e-mail server for you and provides analytics about traffic.
