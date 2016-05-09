---
layout: post
title: Simple Box2D - Custom Polygon creation.
link: http://www.psyked.co.uk/simple-box2d-custom-polygon-creation/
author: psyked_james
description: 
post_id: 1097
created: 2010/01/11 09:09:33
created_gmt: 2010/01/11 08:09:33
comment_status: open
post_name: simple-box2d-custom-polygon-creation
status: publish
post_type: post
---

# Simple Box2D - Custom Polygon creation.

I've been working on some classes to simplify Box2D for Actionscript developers (See [previous post](/actionscript/simplifying-box2das3.htm) for a quick intro).  The latest update to these classes introduces couple of minor ideas, and one gosh-darned awesome idea, if I do say so myself.  Let's start with the awesome things, and move on from there... 

### Awesome thing: Creating Custom Polygons

Or rather the methods for creating them.  Shapes in Box2D come in three basic flavours - circle, rectangle and custom polygon.  Moreover, everything must be convex (no inny bits), have no more than 8 sides, and can't have holes.  On the plus side you can still make larger, more complex objects out of smaller ones - but it all involves a lot of thinking. So, here's the solution - or rather, the options. **Polygon creation option #1 - Creating a polygon from an array of points.** Using some clever triangulation code from [Splashdust.net](http://www.splashdust.net/2009/10/box2d-mouse-drawing-now-with-ear-clipping/), there's a simple method for creating any custom shape from an array of Point objects.  With this method you can create a shape with any number of sides, and not worry about whether the shape is concave or convex.  It'll still break if the edges of your shape interest each other, and doesn't support holes in the objects you're creating, but it's a start. [kml_flashembed movie="http://uploads.psyked.co.uk/2010/01/ComplexPolygonExample.swf" height="280" width="500" /] [sourcecode language="javascript"] var array:Array = [ new Point( 0, 0 ), new Point( 10, 0 ), new Point( 10, 10 ), new Point( 20, 10 ), new Point( 20, 0 ), new Point( 30, 0 ), new Point( 30, 30 ), new Point( 0, 30 ) ]; world.createComplexPolygon( 50, 50, array ); [/sourcecode] **Polygon creation option #2 - Creating a polygon from a shape in a library.** **![](http://uploads.psyked.co.uk/2010/01/flashshapedemo.jpg)** This is where things get cool.  Creating a shape from a series of points is all well and good, but it's a laborious process to set up and modify.  You can create a shape in the Flash IDE, add your symbol to your library and import it to Box2D.  Currently this method only supports single shapes on a single layer, and only straight edges - but multiple shapes, layers and curved edges are definitely on the list for the future. [kml_flashembed movie="http://uploads.psyked.co.uk/2010/01/LibraryShapeExample.swf" height="280" width="500" /] [sourcecode language="javascript"] world.createPolyFromLibraryShape( 300, 100, "sampleShape", "vectorassets.swf" ); [/sourcecode]

### Minor thing #1: Mouse interaction

What fun is a simulation if you can't interact with it? So we now have an easy way to add mouse joints to move things about.  In the next version it's my plan to add a method for filtering out objects, presumably based on each bodies userData. 
    
    
    world.mouseInteraction = true;

### Minor thing #2: Framerate-independent animation.

I stole this idea wholeheartedly from [QuickBox2D](http://actionsnippet.com/?p=1471).  Too good an idea to pass up I'm afraid, this just means that the simulation of the Box2D world is based on a timer, not a framerate.  In theory then, the simulation doesn't slow down or speed up depending on the framerate - which is useful for many things, like graphic-intensive applications and/or memory optimisation. 
    
    
    world.framerateIndependantAnimation = true;

And here's some code for a quick example with framerate independent animation and mouse interaction enabled; [sourcecode language="javascript"] var options:Box2DWorldOptions = new Box2DWorldOptions( 500, 280, 30, 9.8 ); options.setWorldEdges( true, true, true, true ); var world:Box2DWorld = Box2DUtils.createBoxedWorld( options ); world.debugDraw = true; world.mouseInteractExclusions = new Array(); world.mouseInteraction = true; world.framerateIndependantAnimation = true; addChild( world ); [/sourcecode] I've compiled all of my source files into a handy project file if you want to take a look.  Documentation and comments are a bit sparse, but hopefully it'll prove useful! 

## [Download the project files [Zip, 48kb]](http://uploads.psyked.co.uk/2010/01/box2dutils.zip)

![](http://uploads.psyked.co.uk/2010/01/simples.jpg) Simples!

## Comments

**[nanang](#752 "2010-01-11 11:32:00"):** it's so nice

**[reyco](#753 "2010-01-11 18:16:37"):** That's badass stuff man.

**[Geoff Gaudreault](#754 "2010-01-11 19:04:05"):** I created a JSFL a while back that examines a shape and outputs an array of coordinates to the output panel. You could use this in the Flash IDE to automate the process. Contact me if you're interested in adapting it for your use!

**[nikhil](#755 "2010-01-11 23:21:03"):** great work james I just started up with BOX2d and found the limitation on drawing shapes pretty awkward but you gave the solution kudos!

**[James](#756 "2010-01-12 12:56:44"):** @Geoff - Sounds like a cool solution, just a different approach. I'm trying to keep things on a more dynamic class-only based approach at the moment so I don't think I could use anything from the JSFL, but I'd love to see your solution none-the-less. @nikhil - Glad you like it! It's still in development of course, and I'm planning to make things a little more self-explanatory when I get round to documentation. Give me a shout if you have trouble using the classes - in retrospect I didn't make this post too easy to follow!

**[guillaume](#757 "2010-01-31 18:04:11"):** I James, Thanks for your work, which version of B2d do You use ? 2.1? Thanks!

**[James](#758 "2010-01-31 21:24:31"):** I think this is using version 2.0.1, rather than the recently released version 2.1 - I used the latest version of the Box2DAS3 project (before the transition to 2.1) as the basis for my code. Haven't had a chance to update things to the 2.1 version yet though.

**[Rami](#759 "2010-05-31 10:41:19"):** Any chance we will see an pdatae to 2.1 version?

**[James](#760 "2010-06-02 23:25:30"):** There's a chance I'll be able to update things to Box2D version 2.1 and add some better documentation - but no timescales for that yet.

**[tresloukadu](#761 "2010-09-21 12:30:59"):** what version of library are you using? If is a old one please update the post.

**[James](#762 "2010-09-21 22:19:45"):** I'm afraid it's still using Box2D version 2, rather than 2.1. Version 2.1 proved a little hard to adapt my code to and it got bumped down the priorities and forgotten about!

**[adn](#763 "2010-11-02 16:16:39"):** Hi, I've done this BitmapScaner class http://audionysos.cba.pl/bmscaner.html which returns arrays of vertices. The thing is that i have no idea how to create static object with this Custom Polygon creation. Can You tell me??

**[william](#764 "2010-11-03 05:50:41"):** Has anyone gotten this to work within the FlashCS5 Professional IDE?

**[adn](#765 "2010-11-03 20:37:10"):** I have CS5

**[mnu7](#766 "2010-11-14 11:44:17"):** Has anyone gotten this to work within the FlashDeveloper IDE?

