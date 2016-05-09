---
layout: post
title: Tweener and "256 levels of recursion were exceeded in one action list"
link: http://www.psyked.co.uk/tweener-and-256-levels-of-recursion-were-exceeded-in-one-action-list/
author: psyked_james
description: 
post_id: 305
created: 2008/10/13 09:30:52
created_gmt: 2008/10/13 08:30:52
comment_status: open
post_name: tweener-and-256-levels-of-recursion-were-exceeded-in-one-action-list
status: publish
post_type: post
---

# Tweener and "256 levels of recursion were exceeded in one action list"

Tweeners' great, but I came across one little problem the other day: when I tried to remove an externally loaded swf from the stage while it was mid-animation, Tweener could bring the whole Flash movie to a halt with the error '256 levels of recursion were exceeded in one action list'. Obviously that's bad - because this particular error completely stops the flash player with no warning to the end user.  And the fact that external content - which I have no control over - can cause this is doubly bad. All is not lost however, because Tweener has a useful little function: **Tweener.removeAllTweens();** ok, so it can interfere with everything on your flash movie as well, but at least it's stopping the recursion errors. So, if you try to remove a loaded swf file with .removeMovieClip(), you might find that it's using Tweener.  And if so, call Tweener.removeAllTweens() before you call .removeMovieClip() and you'll be fine.  Phew! case closed.

## Resources;

  * [Tweener Documentation](http://hosted.zeh.com.br/tweener/docs/en-us/) \- [removeAllTweens();](http://hosted.zeh.com.br/tweener/docs/en-us/methods/Tweener_removeAllTweens.html)

## Comments

**[lee](#446 "2008-10-13 16:05:11"):** There's also good ol' removeTweens() Tweener.removeTweens(target:Object [, property1:String, property2:String, ...]):Boolean; http://hosted.zeh.com.br/tweener/docs/en-us/

**[Fran](#447 "2008-10-23 09:30:52"):** Thanks for this - in my case Tweener caused this error to be thrown when calling a shift to another scene. Calling this before that action fixed it. I know I would have been pulling my hair out over this for hours ; )

**[Dave](#448 "2009-01-27 21:49:31"):** Two days off hell at work, then I found this article :) thanx!

**[dave](#449 "2009-10-16 02:22:41"):** This does remove a all tweens, however, if an onComplete function is called, that function is still called at the end of the amount of time any tweens would have taken! How does one deal with that, as this will cause errors in some cases!

**[ben](#450 "2009-12-10 15:57:40"):** Thank god I stumbled upon this! I had a similar problem to Fran where this would come up if I interrupted an animation with a button click mid flow. I had to call removeTween on each button but it works! Thanks so much James!

**[Mcfingers](#451 "2011-01-06 15:31:42"):** Great great great article !!! Thanx 4 the tip !

