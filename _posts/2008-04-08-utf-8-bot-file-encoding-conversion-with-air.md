---
layout: post
title: UTF-8 Bot - file encoding conversion with AIR
link: http://www.psyked.co.uk/utf-8-bot-file-encoding-conversion-with-air/
author: psyked_james
description: 
post_id: 208
created: 2008/04/08 01:23:09
created_gmt: 2008/04/08 00:23:09
comment_status: open
post_name: utf-8-bot-file-encoding-conversion-with-air
status: publish
post_type: post
---

# UTF-8 Bot - file encoding conversion with AIR

Well, here it is, my first Adobe AIR application from Flash. ![utf-8bot.png](http://uploads.psyked.co.uk/2008/04/utf-8bot.png) What does it do? Well, it takes an ANSI or Latin1 encoded text file, and spits it out in UTF-8 format. The need is pretty basic, and as is the core code, but it did give me an opportunity to delve into some of the ActionScript libraries that come with AIR. Mainly connected with the **FileSystem**, **NativeDragDrop **and classes related to custom chromes. I particulary like the drag and drop classes - they turned out to be far easier than I'd expected. FileSystem on the other hand, turned out to be a bit more of a bugger to get working correctly. I was also mildly surprised how easy it was to lock the application to the bottom of the screen, just with some cunning use of `stage.maximise` and `stageAlign.BOTTOM`. Anyway, I hope I can write some more in detail 'tutorials' about a few of the things I've learnt at a later date, and take you through the code, but for now... **[Download the AIR File](/downloads/UTF-8 Bot.air) (Requires the [Adobe AIR Runtime](http://get.adobe.com/air/))** **[Download the source code](http://www.psyked.co.uk/wp-content/uploads/2008/04/UTF-8_Bot_Source.zip) (Requires Flash CS3)** Oh, and a little disclaimer; I've tested this repeatedly, and not noticed any problems, but just you know, be careful and don't put anything crucial into the application. This is an experimental project, not a commercial one.

## Comments

**[James](#303 "2008-04-08 12:37:48"):** Oops. I told you it was experimental, and just to prove it so, [Pauls](http://www.mmtdigital.co.uk/RVEa3bf72d6214645bd84d2cae9bb8c0f24,,.aspx)' just pointed out that it doesn't actually save the files out as UTF-8 anymore. It did at one stage in the development, I assure you!

