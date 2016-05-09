---
layout: post
title: Actionscript 2 to Actionscript 3 communication? try FlashInterface...
link: http://www.psyked.co.uk/actionscript-2-to-actionscript-3-communication-try-flashinterface/
author: psyked_james
description: 
post_id: 278
created: 2008/08/20 09:00:38
created_gmt: 2008/08/20 08:00:38
comment_status: open
post_name: actionscript-2-to-actionscript-3-communication-try-flashinterface
status: publish
post_type: post
---

# Actionscript 2 to Actionscript 3 communication? try FlashInterface...

As you probably know, Actionscript 2 and Actionscript 3 projects aren't completely compatable - they can't be, what with all the changes under the hood.  Migrating your own coding techniques is hard enough, but migrating projects can be so much easier and nigh-on-impossible.  So, how could you make a mish-mash of Actionscript 2 and Actionscript 3 movies play nice? Well, there's a few solutions, and several classes that claim to do the job, but the best I've found is [FlashInterface](http://www.flashextensions.com/products/flashinterface/examples/01_flashinterface_avms.html).  It might take a bit of figuring out at first, but the Events based model means that I find it quite easy to use.

## Links

  * [FlashInterface demonstration](http://www.flashextensions.com/products/flashinterface/examples/01_flashinterface_avms.html).

## Comments

**[IanT](#409 "2008-08-20 10:36:28"):** Hi James, Just for info, FlashInterface works fine if you're in a web browser - but if you're in AIR or some other projector-based environment, unfortunately it doesn't work. At that point you need to fall back on a LocalConnection-based solution; we currently use Grant Skinner's [SWFBridge](http://www.gskinner.com/blog/archives/2007/07/swfbridge_easie.html). (However, having done a lot of work on this, AVM1/AS2 support when running inside AVM2/AS3 is very buggy; I don't recommend it.) Ian

**[James](#410 "2008-08-20 11:00:34"):** Ah - its a shame FlashInterface doesn't work for the non-browser based movies, but at least I know that now!

