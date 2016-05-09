---
layout: post
title: MovieClip Saturation Class - ActionScript 2
link: http://www.psyked.co.uk/movieclip-saturation-class-actionscript-20/
author: psyked_james
description: 
post_id: 115
created: 2007/09/04 23:19:37
created_gmt: 2007/09/04 22:19:37
comment_status: open
post_name: movieclip-saturation-class-actionscript-20
status: publish
post_type: post
---

# MovieClip Saturation Class - ActionScript 2

This ActionScript 2.0 Class enables you to easily adjust the colour saturation of any Flash MovieClip during runtime. It requires Flash Player version 8 or above, and uses the ColourTransformationMatrix and some clever jiggery-pokery to adjust the RGBA channels of your MovieClips. In short, it's sweet - and fills a gap in the built-in flash filter classes. Have a look at this flash movie (below) to see the end result, all generated from the same MovieClip. [kml_flashembed movie="http://www.psyked.co.uk/downloads/SaturationManagerTest.swf" height="365" width="470" fversion="8" wmode="transparent" menu="false" /]  Now, before I go much further, I should point out that the functions that make this possible are down to [senocular](http://www.senocular.com/flash/source.php?id=0.169), whose equally awesome code this is based on. All I really did was figure out a way to turn it into an ActionScript 2.0 Class. - Technically it doesn't even need to be in a class - but it just makes things easier. 

### Using this Class

Firstly, you're going to want to [download the source files](/wp-content/uploads/2007/09/SaturationManager.zip). It's as basic as it comes - using it 'out-the-box' requires that you take the 'mmt' folder, and paste it into the same directory as your .fla file. And then, by typing; `mmt.SaturationManager.setSaturation(your_movieclip, the_saturation);` You'll be able to modify the colour saturation of the MovieClip. "`your_movieclip`" is obviously a reference to the MovieClip, and "`the_saturation`" is a value from 0 (No Colour) to 100 (Normal Colour). You can apply values beyond 0 and 100, and oversaturate the colours. In our example (above) the [1st on the left, bottom row] MovieClip is oversaturated, at 150%. 

### Downloads

[Download the source files, containing example .fla and .as files](/wp-content/uploads/2007/09/SaturationManager.zip) [ZIP, 488KB] [Download only the .as file](/downloads/SaturationManager.as) [ActionScript File, 1KB]

## Comments

**[Steven Archer](#173 "2007-10-06 15:00:19"):** Thanks very usefull.

**[Jadon](#174 "2007-12-27 01:02:05"):** Thanks mate. Came in handy :)

**[Wout](#175 "2008-02-08 22:15:50"):** Thanks, I was looking for some saturation formulas to program one myself, but since I'm on a tight schedule for the moment, this class comes in more than handy! Great job!

**[Tim](#176 "2008-02-25 12:11:42"):** You legend - this worked perfectly. I Googled a lot on the matter and this is by far the best example. Thanks again and keep up the good work!

**[Martin Bartels](#177 "2008-02-28 16:20:30"):** Is it possible to use your class when I first load an external jpg file into a movieclip and then try to change the saturation?

**[James](#178 "2008-02-29 09:20:57"):** @Martin - it should be fine, you can apply the saturation changes at any point in your timeline / code.

**[Sniffer](#179 "2008-03-01 20:17:50"):** I have a jpg into a movie, with 26602 pixels wide and 100 pixels tall (719Kb in disk). And it doesn't work. Do you know something about size limitations (file size and/or image size)? Thank you. PS.: I've tested with normal images and it worked just fine.

**[Sniffer](#180 "2008-03-01 20:31:31"):** Duh! I've found: there is a 2880 pixels limit. Thanks anyway.

**[Up to my ears in Flash](#181 "2008-05-06 20:05:27"):** a million thank yous for such a great design and such ease of implementation. more more!

**[C-Check](#182 "2008-05-22 22:32:01"):** I'm using your class for an e-vite I'm making. It's a great idea, but I'm worried that the setup of the class is causing an error with a movieClip that's in motion; I have a movieClip containing an image and an AS function which creates an onEnterFrame to desaturate the image over the course of 30 frames or so. On the main timeline, this movieClip is sliding from right to left with a tween. If I call the function in the movieClip to begin desaturation, the saturation class works, but the movieClip becomes stationary, ignoring the tween. I assume the problem is that a tween can't access an mC that's being acted on by the saturation class (because it can act on the mC if the onEnterFrame doesn't actually call the saturation class but merely traces numbers, or something). Am I missing something obvious or can you think of an easy fix? It's been a long day and I might just have missed something or not understand something...

**[James](#183 "2008-05-23 08:26:28"):** @C-Check - That's an interesting one, and one I haven't come across before. I would imagine that the main issue is coming from the combination of Timeline and Actionscript effects, although that's just a supposition. Actually, a Google on ColorMatrixFilter (the basis for this class) confirms that there might be a few issues with Tweening this filter altogether. Have you tried applying the class on a Keyframe-by-keyframe basis, rather than scripting it? I know it's not pretty, but it might work! I'll have a look at improving the class in the meantime, but I make no promises about timescales...

**[eerkmans](#184 "2008-05-28 15:39:20"):** Just what I needed! thanks!

**[Umar](#185 "2008-06-17 09:54:54"):** guys this is really useful post but can anyone please email me how to use this if i want to use saturation for a movie clip and it should change the color with tween, i will be really very much thankful

**[Brad](#186 "2008-07-02 19:20:38"):** C-Check - I ran into the same issue when trying to use an onEnterFrame to decrease saturation while using a frame-based tween, so I decided to use the same onEnterFrame to move the movieclip, (as well as desaturate) and it worked like a charm. Example: _var saturation:Number = 100; function decreaseSaturation() { test_mc.onEnterFrame = function() { if( saturation > 0 ) { saturation -= 2; } else { saturation = 0; } setSaturation(this, saturation) this._x += ( 400 - this._x ) *.05; this._xscale += ( 50 - this._xscale ) *.2; this._yscale += ( 50 - this._yscale ) *.2; } }_

**[taylor](#187 "2008-12-19 17:48:54"):** Is there any way to import this class from the Classes folder and call it with a function? That way I can use it without having to always copy the class to my current project folder. ex.: import com.mmt.*; SaturationManager.setSaturation(graphic, 15);

**[James](#188 "2008-12-19 21:21:06"):** @taylor - you can always set class library paths in the Flash IDE, through the preferences screen. The default preferences map to the same location as the .fla file, but you can specifiy new locations through Edit > Preferences > Actionscript > Actionscript settings

**[mincartoon](#189 "2009-03-02 14:23:03"):** Thanks man it's so useful!!! :)

**[Lartar](#190 "2009-07-31 23:42:51"):** is there a way to make the saturation script work on mc more than 2880 of width??? I love this script cause i try to make one before without no luck... If there a way to make that please i will love the help... thanks...

**[James](#191 "2009-08-03 21:13:55"):** Lartar - I don't think you can get this to work with images over 2880 width - that's the technical limit of the Flash Player pre-version 9. To get around that limit you'd need to build your code for Flash Player 10 and in Actionscript 3. The alternative is building a clever bitmap tiling solution.

**[Lartar](#192 "2009-08-03 22:23:32"):** Thanks anyway, i make the class working with a very nice script, but the cpu work is too hard on my project so i make a different effect to make it done. Very nice class :) Thanks

**[Frequency650](#193 "2009-09-04 15:07:59"):** Great tool!...even at 2 years old.

**[Seth Taylor](#194 "2009-09-29 23:36:14"):** Thanks. This helped a lot in the flash project of desaturating a bunch of logos.

**[mikod](#195 "2010-02-03 15:01:43"):** This saved sooooooo much time, Thanx thanx thanx

**[Falcon](#196 "2010-05-04 12:40:58"):** Thanks..I used your great script with my video player..

**[Waldorf](#197 "2011-01-01 07:25:11"):** Awesome!!! Direct and straight forward!!

**[Dante](#198 "2011-10-19 07:09:29"):** Awesome i love it, thank you very much!

**[Nathalie](#199 "2013-05-29 17:34:42"):** Exactly what I was searching for. Works just fine for me.

