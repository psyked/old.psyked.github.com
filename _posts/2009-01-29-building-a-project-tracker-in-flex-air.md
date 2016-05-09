---
layout: post
title: Building a project tracker in Flex & AIR
link: http://www.psyked.co.uk/building-a-project-tracker-in-flex-air/
author: psyked_james
description: 
post_id: 665
created: 2009/01/29 10:08:10
created_gmt: 2009/01/29 09:08:10
comment_status: open
post_name: building-a-project-tracker-in-flex-air
status: publish
post_type: post
---

# Building a project tracker in Flex & AIR

![Bug Tracking in Flex & AIR](http://uploads.psyked.co.uk/2009/01/bugsummary.jpg) Ok, this isn't going to be a tutorial - not yet anyways.  So many projects, so little time to write about them. As part of my attempts to improve the way I work, I've been on the look out for a private hosting solution for Subversion, that comes with project management tools like bug reporting, and - crucially - an API that I can work with in Actionscript.  My rather uninspired image above is the first draft of my bug tracking tool. ![Unfuddle Screenshot](http://uploads.psyked.co.uk/2009/01/unfuddle.jpg) My searching has led me to a website called [Unfuddle](http://unfuddle.com/), which offers all of these things.  They have an API that works around url requests and HTTP headers authentication, which means that in theory (and practice) I can write Actionscript that can retrieve and write information to my unfuddle account.  All of their examples are in curl(!), but the principles are easy enough to translate, which is what I'm working on right now in Flex.  Once I have things a little more concrete, I'll post a proper tutorial of some sorts. Unfuddle offers free accounts, as well as paid ones so if you wanna do the same as me, give it a whirl.  I've even posted a small [Flex example in the community forums](http://unfuddle.com/community/forums/6/topics/462) over at Unfuddle.

## Comments

**[Joeflash](#537 "2009-01-30 01:33:38"):** Unfuddle is a good deal if you've got lots of members which don't use a lot of space. But my experience has been that RIA development, if you're checking in fonts and graphical assets including PSD source, can go way beyond half a meg. And have more than a few projects, and you're over the 2GB at $24/mo pretty quick. Assembla gives you $3/GB/mo, but it costs to have a large team unless they're on multiple projects. And Assembla has way more features if your needs expand later. I don't work for them, but I've been using them for nearly six months and I'm impressed. I don't know if they have a backend API or not. Compare [Unfuddle's plans](http://unfuddle.com/about/tour/plans) with [Assembla's plans](http://www.assembla.com/plans).

**[James](#538 "2009-01-30 14:35:45"):** My current plans aren't likely to include a lot of storage space, but I can see how it would get expensive. It looks like Assembla also has a pretty good API for everything but it doesn't look like there's a 'free trial' option, which is basically what I'm using now to get a feel for it all. Thanks for the links - interesting comparisons!

