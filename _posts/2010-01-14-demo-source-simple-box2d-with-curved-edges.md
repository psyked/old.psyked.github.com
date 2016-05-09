---
layout: post
title: Demo & Source: Simple Box2D, with curved edges!
link: http://www.psyked.co.uk/demo-source-simple-box2d-with-curved-edges/
author: psyked_james
description: 
post_id: 1114
created: 2010/01/14 00:38:35
created_gmt: 2010/01/13 23:38:35
comment_status: open
post_name: demo-source-simple-box2d-with-curved-edges
status: publish
post_type: post
---

# Demo & Source: Simple Box2D, with curved edges!

[kml_flashembed movie="http://uploads.psyked.co.uk/2010/01/CurvedShapeExample.swf" height="280" width="500" /] (The image above this text is actually the Flash movie, if you hadn't guessed.  Try using your mouse to interact.  If it's blank, then something's gone wrong!) I've been busy working on my Box2D classes again. (As before [here](/actionscript/simplifying-box2das3.htm) and [here](http://www.psyked.co.uk/box2d/simple-box2d-custom-polygon-creation.htm).)  I'm not quite ready to go through the code with some tutorials yet, but you can [download the source for this demo here](http://uploads.psyked.co.uk/2010/01/simplebox2d_demo_100113.zip).  This version has had a bit more of a proper code cleanup - I've un-hacked some hacks I did earlier in development, and added a few more utility functions, but most importantly this version supports SWF library asset importing of multiple shapes, and shapes with curved edges (which it couldn't do previously). I feel like I should put that in bold or something, because it's probably my most-clever bit of code to date.  I'm going to settle for saying it twice though: You can import library objects with multiple shapes, and shapes with curved and straight edges.  Have a look at the screenshot below and compare it with the Box2D display; **In Flash IDE:** **![](http://uploads.psyked.co.uk/2010/01/flashview.jpg)** **In Box2D:** **![](http://uploads.psyked.co.uk/2010/01/box2dview.jpg)** You can [download the source for this demo here](http://uploads.psyked.co.uk/2010/01/simplebox2d_demo_100113.zip). I'm going to get this as a project on some publicly-available source repository soon.  I'd love to hear feedback on it now though!

## Comments

**[reyco](#778 "2010-01-14 16:10:07"):** Looking real good James! Nice Job!!

**[chichlatte](#779 "2010-03-04 17:32:11"):** Just superb. Makes box2d something you can play with rather than wrestle with. I'm going to build something fun with this as soon as i get a minute :)

**[James](#780 "2010-03-05 00:25:45"):** Let me know how you get on! The latest post on this is [here](http://www.psyked.co.uk/box2d/simple-box2d-better-cleverer-more-optimised.htm) and the source code is also available from GitHub [here](http://github.com/psyked/Simple-Box2D).

**[T](#781 "2010-03-23 13:08:17"):** outstanding! I may branch out an update for 2.1a if it's not already in the works in a month or two.

**[James](#782 "2010-03-24 23:53:18"):** @T I'm not currently updating things to the 2.1 version myself, so please feel free to branch things!

**[Lavon Woods](#783 "2010-06-19 02:27:53"):** Awesome post man, I borrowed your idea of importing assets from the flash IDE and integrated into my soon to be released Isometric component. http://hybridmindset.com/blog/My-PushButton-Engine-Experience-Week-2

**[James](#784 "2010-06-21 09:13:12"):** Sounds like a cool idea Lavon!

