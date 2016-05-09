---
layout: post
title: I hate using AVM1Movie...
link: http://www.psyked.co.uk/i-hate-using-avm1movie/
author: psyked_james
description: 
post_id: 1262
created: 2010/11/23 00:20:19
created_gmt: 2010/11/22 23:20:19
comment_status: open
post_name: i-hate-using-avm1movie
status: publish
post_type: post
---

# I hate using AVM1Movie...

![](http://uploads.psyked.co.uk/2010/11/avm1movie-hydra.jpg) Developer beware.  AVM1Movie content (running ActionScript 2 content inside ActionScript 3 movies) is a spiralling nexus of doom that will lead to your eventual insanity, if you persist in walking down that path. Seriously.  I'd love to catalogue the many intricacies and weird behaviours of AVM1Movie content, but that would mean being able to understand and explain them - which I can't do. The bottom line is that ActionScript 2 content in an ActionScript 3 movie doesn't behave the same as an ActionScript 2 movie does on its own.  Certain things just flat-out don't work, or don't work 'a certain way'.  Others that you thought did work actually work slightly or completely different, but do start working correctly with some encouragement. 

### Want some examples?

Goodness knows if they're always repeatable, but these certainly happened to me... 

  * In AS2, draw a rectangle, with a width of 130 pixels.  Measure the width.  What is the width, according to Flash? 89 pixels.  Fan-tastic.  Cast the width as a Number (even though it was already a number) before you start drawing, and try again.  What is the width this time, according to Flash? 130 pixels.
  * Dynamically generate an XML structure in AS2, using the **addElement **or **createElement **methods.  It works in AS2 on its own, nothing works when it's loaded as AVM1.  Rewrite the function to create everything as a String and call **parseXML** on it.  It all works.
  * Try calling a function.  Function doesn't work.  Set an enterFrame listener, and call the function a single frame later.  It works.
AVM1Movie has done its utmost to ruin my sanity - don't let it ruin yours. Avoid doing anything technically complicated in it, rewrite it all in AS3 if you can!

## Comments

**[a_[w]](#871 "2010-11-23 20:51:21"):** Looks like you never used AS2 or AS1. First and last is a normal behaviour in most cases. I've worked a lot with both and have done integration between eachother and can't say that I had some special challenges. All quite understandable.

**[James](#872 "2010-11-24 00:45:12"):** Oh I've used them... maybe I forgot how bad they were, being spoiled by reliability n'all!

**[Javier Reinoso](#873 "2011-06-04 06:24:12"):** Well, understand, some programmers not have time for lost in conversions and have many good code made in as2, the action of adobe to do problems in work many years of work of millions of programmers are criminal... You not like as2, well, good, is sure you not make many years creating good code in as2, and not lost your work... But cvonvert many codes are time, and some programmers need time for our programs, not for conversions!!!

**[Javier Reinoso](#874 "2011-06-04 06:29:55"):** In your photo you appear to be very young, you not lost many years of good programation for the dirty action of adobe for not do support to as2 codes... Adobe have compatibility of as2 in web browsers, why??? Simple, if not do support, millions of webs kaput!!! and is a very bad publicity for the company, because this do support, and if do support, have the possibility, why not do support in developpers tools??? Adobe are playing with the effort and work of many millions people and many years of work, I think is needed block adobe, is a dirty company playing with the work of millions of programmers...

**[Javier Reinoso](#875 "2011-06-04 06:32:53"):** Translate to as3 are many time, and I, for example, have good codes in as2 and not have time for lost for translate, adobe need to create a good tool for convert as2 to as3, or do support to as2 in as3 tools!!! If not, is a dirty action, a dirty company, many and very dirty action... Not serious, not responsible, and not with good intention...

