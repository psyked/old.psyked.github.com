---
layout: post
title: Debugging Flash Movies with Fiddler 2
link: http://www.psyked.co.uk/debugging-flash-movies-with-fiddler-2/
author: psyked_james
description: 
post_id: 126
created: 2007/10/07 10:14:19
created_gmt: 2007/10/07 09:14:19
comment_status: open
post_name: debugging-flash-movies-with-fiddler-2
status: publish
post_type: post
---

# Debugging Flash Movies with Fiddler 2

![](http://uploads.psyked.co.uk/2007/10/fiddlerlogo.png)

### What is Fiddler?

_From the [Fiddler website](http://www.fiddler2.com/fiddler2/):_

> Fiddler is a Web Debugging Proxy which logs all HTTP(S) traffic between your computer and the Internet.

Simple really. Introduced to me by [Chris Preece](http://www.mmtdigital.co.uk/RVE9b7ab808a1ad4754a1a5800dce029b34,,.aspx), this is a Microsoft-made free debugging tool which shows you all of the header information and file requests that your browser makes. It's works with IE, and also claims to work with other browsers (I've never tried this though)

### What does it do?

It has many more technical capabilities than those I need, but I found this quite useful for debugging flash movies on live websites. I've never really figured out the whole 'remote-debugging' features of Flash, so Fiddler offers another way of debugging them - showing you all the url requests that the flash movie makes. You can easily identify where things are going wrong once you find your crazy malformed urls in the requests list. 

### Fiddler Links:

Visit the [Fiddler website](http://www.fiddler2.com/fiddler2/). Download [Fiddler 2](http://uploads.psyked.co.uk//2007/10/Fiddler2Setup.exe). Read Developer.com's [getting started with Fiddler](http://www.developer.com/lang/jscript/article.php/3631066) tutorial.

## Comments

**[Fiddling Flasher](#221 "2008-06-03 15:22:13"):** At which point do you discuss debugging Flash with Fiddler?

**[James](#222 "2008-06-04 09:00:06"):** Ok, perhaps the title is a bit misleading - what I meant was that in general, Fiddler can be used to help you debug the http side of things - which is useful when you can't get trace statements from Flash because you're testing things in a browser.

**[amnon](#223 "2010-01-16 01:54:56"):** this is so not a "Microsoft-made debugging tool".

**[James](#224 "2010-01-16 10:53:43"):** @amnon - True, sorry. I must've been misinformed back then. I'll amend the post accordingly.

