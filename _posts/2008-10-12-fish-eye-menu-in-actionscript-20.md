---
layout: post
title: Fish Eye Menu in ActionScript 2.0
link: http://www.psyked.co.uk/fish-eye-menu-in-actionscript-20/
author: psyked_james
description: 
post_id: 304
created: 2008/10/12 14:01:05
created_gmt: 2008/10/12 13:01:05
comment_status: open
post_name: fish-eye-menu-in-actionscript-20
status: publish
post_type: post
---

# Fish Eye Menu in ActionScript 2.0

A little while ago we had to do a Fish Eye menu - the magnification effect you see on the Mac OSX dock menu - but we had to do it in ActionScript 2.0, rather than ActionScript 3.0. Now, [Shine Draw](http://www.shinedraw.com/) have been kind enough to put a version of this out into the wild, but it's in AS3 [[link]](http://www.shinedraw.com/animation-effect/flash-and-silverlight-fish-eye-menu/). Of course AS3 is faster and nicer, but there are still some out there who want their stuff targetted for Flash Player 8 - which means AS1 or AS2 only - so I backwards converted Shine Draw's lovely class-based demo to a timeline-scripted AS2 version. 

## Demo

[kml_flashembed movie="http://www.psyked.co.uk/downloads/fisheyemenu_as2.swf" height="280" width="500" /] **Download:** [Fish Eye Menu [Flash CS3, Flash Player 8, AS3, 110KB]](/wp-content/uploads/2008/10/fisheyemenu_as2.zip)

## The process;

Actually, it wasn't too hard to backwards convert the AS3 version - the three main things to do are to 

  1. Take the code out of a document class structure, and onto the timeline - which in reality is mostly a copy and paste job, a bit of commenting out, and changing the events or function calls that initalise the code.
  2. Change variables and parameters, linkages and library classes; **.scaleX** to **._xscale**, event names and listener arrangements, and library item classes.
  3. Rewrite code dealing with depths or the display list. - This is actually the most difficult part of the conversion, and really highlights how difficult depths were to work with, pre AS3.
There's a little bit of code commenting in there, but if you're interested in seeing how the two compare, I would suggest you head over to Shine Draw, download the AS3 version, download this version, and look at them side-by-side. 

## Resources;

  * [Shine Draw - Flash and Silverlight: Fish Eye Menu](http://www.shinedraw.com/animation-effect/flash-and-silverlight-fish-eye-menu/) (yes, there's a Silverlight equivilent!)
  * **Update:** [The timeline code, available on GitHub](http://gist.github.com/518634)

## Comments

**[David](#440 "2009-02-04 17:13:58"):** Hi. I'm David, from Portugal, and I'm nearly finishing my Design of Communication and Multimedia course, at ETIC. I'm currently working on my portfolio website, and I decided to use a fisheye menu on the galleries, as a way to display the images' thumbnails. I found your AS2 version of the fisheye menu I had found before, but in AS3 (which is completely out of my league). I made a few changes just to make icons a bit smaller and closer, and to place it on the left of the movieclip. But then I ran into 2 problems. 1- How do I make it so the mouse movement only affects the thumbnails (making the fisheye effect) when the mouse is over it? I was trying to make a condition to say that it will only work when the "xmouse" is over 440 - so it's in the area where the fisheye menu is placed (my movieclip dimensions are 560 x 450 px), but I can't get the code right! 2- I'm trying to make the thumbnails into buttons. So I got them to the stage, opened them, and turned the bitmaps inside the movieclips into buttons. I got the "down" stage to work, replacing the image I use as "normal" with another that I created to be that "down" stage, and it works. It recognizes the button and it's "down" stage when I press it, but now I'm trying to make the buttons to work "onPress", using labels (a simple flash gallery). I used the simple code: stop(); b1.onPress = function (){ gotoAndStop("photo1"); }; b2.onPress = function (){ gotoAndStop("photo2"); }; b3.onPress = function (){ gotoAndStop("photo3"); }; b4.onPress = function (){ gotoAndStop("photo4"); }; But it doesn't work! It wont go to the other labels. Can you tell me what I'm doing wrong?! Stay cool! Peace ;p

**[Lars](#441 "2009-06-21 13:20:21"):** This rocks, thanks!

**[Henry](#442 "2010-07-08 16:42:23"):** Gracias por el script!! para la pregunta de David.. si deseas que los iconos se activen en determinado lugar.. o area.. lo puedes hacer manejando porcentajes.. this.onMouseMove = function():Void { //1/3 of stage height if(_ymouse>Stage.height/3) { //Acomplete the Code here.... // } }

**[sapta](#443 "2010-08-11 07:49:42"):** hi... I interest to this sample,,, but can U tell me how to make event every images/button in this menu I will call other swf or frame I need Your help please...

**[James](#444 "2010-08-11 08:37:00"):** I've copied the timeline code across to [GitHub](http://gist.github.com/518634) and will try and have a look at modifying that to add events for you, @sapta.

**[Werbeagentur](#445 "2010-10-02 21:18:20"):** Nice work! we made one working with JavaScript and without any JS-Framework. Probably something also woth to share.

