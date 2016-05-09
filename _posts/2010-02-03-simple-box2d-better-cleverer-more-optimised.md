---
layout: post
title: Simple Box2D - Better, cleverer, more optimised.
link: http://www.psyked.co.uk/simple-box2d-better-cleverer-more-optimised/
author: psyked_james
description: 
post_id: 1169
created: 2010/02/03 09:29:44
created_gmt: 2010/02/03 08:29:44
comment_status: open
post_name: simple-box2d-better-cleverer-more-optimised
status: publish
post_type: post
---

# Simple Box2D - Better, cleverer, more optimised.

![](http://uploads.psyked.co.uk/2010/02/box2d-shapes-2.jpg) _^ This time, that's an image - saves on the page rendering time!_ Another update on the Box2D classes I'm working on.  No new features, but some pretty cool expansions and improvements to the library object creation. If you check out [the previous post](/box2d/demo-source-simple-box2d-with-curved-edges.htm), you'll see that the the dynamically drawn shapes weren't exactly perfect; nor were they very efficient.  Oh they worked fine, and traced the detail of the shape very well - but it took a decent chunk of system resources to animate and ended up with some overlaid shapes; which all made the Box2D a bit sluggish and the behaviours buggy. So, stealing incorporating ideas from other projects has been the name of the game - namely the ear clipping optimisation code from [Splashdust.net](http://www.splashdust.net/2009/10/box2d-mouse-drawing-now-with-ear-clipping/), combined with some of my own cobbled-together more optimised code for tracing curved edges. 

### Live demo:

Mouse interaction is enabled in the below example - click and drag the objects to check out how it works. [kml_flashembed movie="http://uploads.psyked.co.uk/2010/02/LettersExperiment.swf" height="280" width="500" /] 

### [Download the source code for this demo.](http://uploads.psyked.co.uk/2010/02/simplebox2d_demo_100202.zip)

* The source code isn't exactly cleaned up - sometime, eventually, it will be.

## Comments

**[chichlatte](#807 "2010-02-09 22:27:40"):** insanely useful!! thank you :)

**[James](#808 "2010-02-10 12:28:40"):** Thanks! I've just managed to get the source files for this demo on GitHub: http://github.com/psyked/Simple-Box2D Where I'll endeavour to keep all the source files from now on!

**[T](#809 "2010-03-25 02:42:06"):** can't seem to compile the examples (box2dexperiments.as, complexpolygonexample.as, curvedshapeexample.as, etc.) I tried the zip here, and the latest from github - I think it may be because I'm using FlashDevelop instead of Flex? Not sure, I haven't had many problems compiling actionscript files. When I try to compile any of them, I get "psyked-Simple-Box2DBox2DCollisionShapesb2Shape.as(81): col: 36 Error: Type was not found or was not a compile-time constant: b2FilterData."

**[James](#810 "2010-03-25 12:03:54"):** I'm not sure about the b2Shape.as or b2FilterData.as file, they're both in the zip I've just downloaded from GitHub and work when I put it into a new project in Flex Builder. I did notice that the KeyboardManager class was missing for one of the examples, so I'll get that updated on GitHub asap.

**[T](#811 "2010-03-25 13:06:08"):** all resolved, and got it working, thanks! Just had a conflicting library path

**[domi](#812 "2010-03-27 13:30:39"):** hi just wanted to let you know that we can change the max of Polygon Vertices in the file B2D.common.b2eSttings.as. I changed it to 500 and it allowed me to build a perfect sinus wave with that code : ` var pt:int = 500;//pour + de 8 changer b2settings maShapeDef.vertexCount = pt; for (var i:int = 0; i < pt; i++) b2Vec2(maShapeDef.vertices[i]).Set(i/10,Math.sin(i/10)); ` I don't know about the performances, so far I'll use this trick for a static ground shape.

**[James](#813 "2010-03-27 22:46:31"):** @domi - That's quite interesting, I'll have to try it out and see how it goes.

**[domi](#814 "2010-03-28 05:33:18"):** nevermind, could'nt make it work as a ground, other shapes pass trough. or maybe it's just me.

**[James](#815 "2010-03-28 15:24:46"):** @domi - Remember that custom shapes in Box2D have to be concave and specified in a clockwise fashion, otherwise the shape doesn't get created properly - have you checked that's ok?

**[domi](#816 "2010-03-28 16:08:50"):** woops, missed the point they have to be convex. Anyway, box2d can' help me doing my stuff ^^

**[tresloukadu](#817 "2010-09-21 12:14:21"):** hello, the box2d library you use in your example, is a modified one? Because when i tried run your example with my latest box2d library (the stable one not the alpha) it gave lots of errors and warnings.

**[James](#818 "2010-09-21 22:22:52"):** It's using Box2D version 2.0 - a cached copy of the files are stored alongside the example files. The latest version of Box2D is 2.1, but I haven't been able to resolve the compatibility problems with the latest version and this example - apologies for that.

**[adn](#819 "2010-10-20 22:50:23"):** Hi, How i can create (static) complex polygon??

**[RaVeL](#820 "2010-11-02 16:16:33"):** hi adn look here http://www.box2dflash.org/docs/2.0.2/manual#About_3 cheers

**[adn](#821 "2010-11-02 20:44:07"):** Ravel z forum nutera? Już sobie poradziłem z tym... ;)

**[RaVeL](#822 "2010-11-03 08:50:00"):** yes Sir :)

**[adn](#823 "2010-11-03 20:39:55"):** Co durnia zgrywasz ? :P Czemu na forum nie napisałeś?

**[Hyakkidouran](#824 "2011-03-07 13:04:46"):** That is pretty amazing! I tried to take a look at the source and I started wondering... How do you create a box 2D shape from a shape that is in the same swf than the program? I only found a function to import from an external .swf. Your import library is pretty amazing, but I think it forces to put several .swf at a given spot when you want to publish your game, which won't work on newgrounds or any flash game site that isn't your own. If I want to put everything in only one swf, how should I use or edit your library? Thanks in advance for any indication!

**[James](#825 "2011-03-07 22:46:11"):** @Hyakkidouran - Because of the slightly hacky way the library is put together, the only way it's possible to load library objects from the current SWF is to effectively re-load the current SWF, by specifying its filename and file path. To avoid having to hardcode filenames or locations, it's probably possible to use the LoaderInfo class to retrieve URLs.

**[Hyakkidouran](#826 "2011-03-11 11:06:41"):** I see. I'll try to look into that. Thanks for the help.

**[palmer](#827 "2011-09-16 02:06:00"):** **sinusitis...** below are some links I found useful...

