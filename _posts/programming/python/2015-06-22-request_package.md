---
layout: article
title: "02 - Posting to Websites in Python"
description: "How to login and download files from a website using Python."
modified:
categories: programming
subcategories: python
excerpt:
tags: []
image:
  feature:
  teaser: i.png
  thumb:
date: 2015-06-22T10:27:01+02:00
---
{% include toc.html %}

For the last couple weeks I've been doing some house keeping before going on vacation.  I'm working on a paper using PSID panel data and want to do my work in Python.  The problem is that the PSID data comes in SAS format, with a .txt ASCII file containing the data and a .sas (or .do or .spss) file containing instructions on how to interpret the file.  In order to deal with these files, [Florian Oswald](https://floswald.github.io/){:target="_blank_"} has written an R package to download the data and build a panel.  I've been transcribing the package into Python and struggled for several days with posting to the online form in order to login and download data.  This post is about how to do that and what I found to be the easiest solution.

Different Methods to Do the Same things
---------------------------------------
The standard for connecting to a website from Python, R, etc., is cURL, a free software library for transferring data through http.  The problem is that in Python the libcurl wrapper is not at all pythonic.  Unless you are familiar with using http you will struggle, as I did, for days trying to get the functions to work.  As usual, though, there is a module to fix that!

The slogan for the [Requests](http://docs.python-requests.org/en/latest/){:target="_blank_"} module is "HTTP for Humans".  Ah, finally something I can understand!  The module does all of the heavy lifting for you and even anticipates some of your needs.  I encourage you, if you are going to be using it at all often, to get familiar with what the package can do by perusing the read me.  This will also give you a chance to learn about http if you are unfamiliar (as I was).

Requests
---------
So to get started, let's see how to make a simple request (this example is taken from the Requests website).  First, import requests (given that you've already installed the module):

{% highlight python %}
import requests
{% endhighlight %}

Requests is object oriented, so you post requests to a webpage and the generated object contains all of the response information you might need.  For example, run

{% highlight python %}
r = requests.get('https://api.github.com/events')
{% endhighlight %}

The returned `r` object contains a bunch of methods you can use to retrieve information from the returned html.  For instance `r.url` will return the associated `url`, while `r.text` will return the entire `html` webpage.  There a ton of methods that are very useful, so I suggest you get familiar by reading the user guide.

What We Are Going to Do
-------------
So, in order to save time and space I'm going to combine two topics here.  We'll take as a working example posting to the PSID website to login.  If you want to follow along, I suggest you register for an account [here](http://simba.isr.umich.edu/U/Login.aspx){:target="_blank_"}.  The PSID Data Center is what is known as an ASP web application.  That really just refers to the architecture on which the site is built, but it has implicaitons for posting a login to the page.  ASP sites often have different requirements for form fields, or the information they need in order to allow you to login.  Because of this there are two things that you will need to do: scrape and post.

First of all, you must scrape the page.  What does this mean?  To better explain, follow these steps:

* First of all, navigate to the PSID login page linked above.
* Right click on the login field (or anywhere for that matter) and click "Inspect Element".
* Navigate to the network tab and click on the clear button (similar to a ["Do Not..."](https://www.google.fr/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=do%20not%20sign){:target="_blank_"} symbol in the states).
* Now login using your username and password.  In the inspect element field you should see a bunch of information appear.  If not, start over because you must have done something wrong.  My screen looks like this:

![Screen](/images/post_screen.png)

* One of the elements (probably the first) will be `Login.aspx`.  Click on this and it will pop up a frame with several tabs.  Select `Headers`.
* Scroll down to `Form Data`

You made it!  What you are looking at is a list of the required fields to post a login form on the PSID website.  In order for your program to login you must provide all of this information.  When writing a program to post a form, this is the first thing you should do to find out what fields you need to know.

So, in order to login we'll follow the following steps:

1. Post a `request` to the page to retrieve the `html`.
2. "Scrape" the page to find the required form field values.
3. Re-post a `request` to login.

But wait, what is scraping!?  Scraping refers to searching a webpage for key terms.  This is how Google builds its search results (or one of the many steps in what they do).  We don't actually have to do all the work to do this, as [Beautiful Soup](http://www.crummy.com/software/BeautifulSoup/){:target="_blank_"} is going to do all of it for us.  So let's get down to business.

The Initial Get
---------------
Since we've already imported requests, the first thing we'll do is create a `requests` session object and define the login url:

{% highlight python %}
c = requests.Session()
URL = 'http://simba.isr.umich.edu/u/login.aspx'
{% endhighlight %}

Now we want to retrieve the `html` for the page:

{% highlight python %}
page = c.get(URL)
{% endhighlight %}

Next, use the Beautiful Soup package to scrape the page and define a `params` dictionary object that contains all of your form variables:

{% highlight python %}
#Import Beautiful Soup
from bs4 import BeautifulSoup

#Use the beautifulsoup package to scrape for form variables
soup = BeautifulSoup(page.content)
viewstate = soup.findAll("input", {"type": "hidden",
                         "name": "__VIEWSTATE"})
radscript = soup.findAll("input", {"type": "hidden",
                         "name": "RadScriptManager1_TSM"})
viewstategenerator = soup.findAll("input", {"type": "hidden",
                                  "name": "__VIEWSTATEGENERATOR"})
eventvalidation = soup.findAll("input", {"type": "hidden",
                               "name": "__EVENTVALIDATION"})
radscript = soup.findAll("input", {"type": "hidden", "name":
                         "RadScriptManager1_TSM"})

#Gather form data into a single dictionary
params = {'RadScriptManager1_TSM': radscript[0]['value'],
          '__EVENTTARGET': '',
          ' __EVENTARGUMENT': '',
          '__VIEWSTATE': viewstate[0]['value'],
          '__VIEWSTATEGENERATOR': viewstategenerator[0]['value'],
          '__EVENTVALIDATION': eventvalidation[0]['value'],
          'ctl00$ContentPlaceHolder1$Login1$UserName': USERNAME,
          'ctl00$ContentPlaceHolder1$Login1$Password': PASSWORD,
          'ctl00$ContentPlaceHolder1$Login1$LoginButton': 'Log In',
          'ctl00_RadWindowManager1_ClientState': ''}
{% endhighlight %}

You'll want to replace `USERNAME` and `PASSWORD` with your own.  Notice that I left some of the form fields blank.  This is because they are blank whenever I submit this form, but I kept them here in case it is different for others.

Now, post the form:

{% highlight python %}
c.post(URL, data=params, headers={"Referer": "http://psidonline.isr.umich.edu/"})
{% endhighlight %}

Here the `headers={"Referer": "http://psidonline.isr.umich.edu/"}` tells the website that you came from within the site and are not just posting the form directly (which is actually what you are doing, but the site doesn't seem to like that...).  Now the reason for using the session object should become clear.  `c` now contains a cookie that you can use to move within the site.  For example, let's say you wanted to download a the zipped family interview files from 1968.  Then you could simply run the following line:

{% highlight python %}
data = c.get('http://simba.isr.umich.edu/Zips/GetFile.aspx?file=1056',
             allow_redirects=False)
{% endhighlight %}

Now `data` contains a binary zip file with the data you requested.  You can use the ZipFile module to unzip and save this, but that's for another post!

Conclusion
----------
Overall, posting to webpages is not something that I or other economists need to do very often.  However, when we do need to do it it is because we need data.  These data files can sometimes be large or there could be many of them.  Using the `requests` package to automate logging into a database can save us tons of time, as we can let the computer do all of the work for us!  In any case, if you have any comments or questions, please let me know!
