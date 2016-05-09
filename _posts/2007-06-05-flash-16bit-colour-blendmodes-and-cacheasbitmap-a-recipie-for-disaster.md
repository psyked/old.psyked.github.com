---
layout: post
title: Flash, 16bit colour, blendModes and cacheAsBitmap.  A recipie for disaster?
link: http://www.psyked.co.uk/flash-16bit-colour-blendmodes-and-cacheasbitmap-a-recipie-for-disaster/
author: psyked_james
description: 
post_id: 62
created: 2007/06/05 13:07:12
created_gmt: 2007/06/05 12:07:12
comment_status: open
post_name: flash-16bit-colour-blendmodes-and-cacheasbitmap-a-recipie-for-disaster
status: publish
post_type: post
---

# Flash, 16bit colour, blendModes and cacheAsBitmap.  A recipie for disaster?

Apparently so. For one of our recent projects, we've been plagued with reports of a 'Black screen of Death' - where our program would seize up and keel over whilst using our interactive drawing tools. This seemed to happen on approximately 3% of our test bed, but none of our development machines. One of 'those' bugs. Today, however, I believe I've cracked it. (Thanks to some feedback that isolated the problem only exists on machines running in 16bit colour mode.) If, say, you're foolish enough to try using Flash 8's blendModes and cacheAsBitmap features in a machine running in 16bit colour mode, your cached MovieClips can turn out solid black. Now, obviously it's down to some kinda colour mathematics, but the important thing is that it can be fixed by removing the bitmap caching. So, if for some freaky reason you get a similar problem - remove your bitmap caching. {End Public Service Announcement}