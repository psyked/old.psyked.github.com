---
layout: post
title: Simplifying Box2DAS3...
link: http://www.psyked.co.uk/simplifying-box2das3/
author: psyked_james
description: 
post_id: 1089
created: 2010/01/08 09:25:15
created_gmt: 2010/01/08 08:25:15
comment_status: open
post_name: simplifying-box2das3
status: publish
post_type: post
---

# Simplifying Box2DAS3...

One of the downsides to the Box2DAS3 project - and probably one of the major hurdles to most Flash developers - is the fact that it's inherited a lot of the syntax from the C++ project that it's derived from.  Maybe it's just because we're used to it, but Actionscript is pretty easy to understand, and its methods of working pretty tolerant of inefficient coding. C++ - or whatever Box2D is written in - is not, and it's a little painful to setup and easy to break.  For my sanity as much as anyone else's I'm working on a set of classes in AS3 that wrap around the Box2DAS3 classes, and provide you with a more familiar syntax for working with Box2D - objects, methods and utilities that makes it quicker to throw things together and don't require you to rethink the way you work. Well, that's the eventual aim anyway. Here's the result of the first round of development - creating a Box2D world and adding objects, in about 6 lines of code. [sourcecode language="javascript"] var options:Box2DWorldOptions = new Box2DWorldOptions( 500, 280, 30, 9.8 ); options.setWorldEdges( true, true, true, true ); var world:Box2DWorld = Box2DUtils.createBoxedWorld( options ); world.debugDraw = true; world.animateOnEnterFrame = true; addChild( world ); for ( var i:int = 0; i < 30; i++ ) { world.createCircle( 500 * Math.random(), 280 * Math.random(), 50 * Math.random()); } [/sourcecode] And here's the result: [kml_flashembed movie="http://uploads.psyked.co.uk/2010/01/Box2DExperiments.swf" height="280" width="500" /] Not at the point of getting any interaction, or anything more interesting yet, but I've create a utility class for creating Box2D worlds and a Box2DWorld class (as opposed to b2World, which it extends).  The aim of these classes is to condense about 40 - 60 lines of initialisation and basic scenarios into just a few lines, using default variables whilst still allowing for optional overrides.  So if you wanted a world with 0 gravity, that's just a case of changing it at the start. I'll post the classes soon - just as soon as I decide the best way to do so.  It'll all become more clear then, I hope.

## Comments

**[leef](#742 "2010-01-08 10:23:24"):** Thanks James! I'll be watching = )

**[Andy](#743 "2010-01-08 10:44:03"):** Great stuff, you know you could actually make some money of this, either via donations or some other means... The people at FGL would probably be very interested in this, you should check it out, even sign up :-) www.flashgameslicense.com

**[James](#744 "2010-01-08 11:22:11"):** Hmm, maybe that WordPress donations plug-in isn't a bad idea! I'll check out FGL as well...

**[Eric Holm](#745 "2010-01-08 11:33:20"):** Have you seen this project? http://actionsnippet.com/?page_id=1391

**[reyco1](#746 "2010-01-08 14:32:09"):** I actually created a wrapper library for Box2DFlashAS3 some time back because of the same reasons : http://blog.reyco1.com/box2dwrapper-box2dflashas3-made-simple/

**[James](#747 "2010-01-08 15:55:14"):** It appears the idea of an AS3-syntax wrapper for Box2D is not quite so original as first thought! QuickBox2D - I saw it when I started learning Box2D, but never really picked it up. Looks good, and definitely has a few ideas I'll pinch myself. Not quite sure why I didn't try it out - but at least when I write my own classes I can extend them easier (I have some crazy things planned). @reyco1 - Cool wrapper library - amazing how similar the solutions are already!

**[James](#748 "2010-01-10 11:48:14"):** Quick update for y'all - next version has some cleverness for creating complex, convex polygons - from points in an Array and even library shape data. Releasing as soon as I've finished cleaning up the code!

**[mnu7](#749 "2010-11-12 12:37:10"):** how to add any other object other than polygons I like to add image in place of polygons.

**[MC](#750 "2011-01-30 09:20:38"):** Great! Any chance to port this to the last Box2D version? (2.1a) Regards

**[James](#751 "2011-02-02 10:18:25"):** Unfortunately no - no immediate plans to update to Box2D 2.1. I've tried once, but it blew my mind trying to make the changes to 2.1.

