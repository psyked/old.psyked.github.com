---
layout: post
title: ImageSizer -- and beyond(!)
link: http://www.psyked.co.uk/imagesizer-and-beyond/
author: psyked_james
description: 
post_id: 1251
created: 2010/07/29 00:10:06
created_gmt: 2010/07/28 23:10:06
comment_status: open
post_name: imagesizer-and-beyond
status: publish
post_type: post
---

# ImageSizer -- and beyond(!)

It's been a couple of years since I either started working on [ImageSizer](http://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.offering&offeringid=10740&marketplaceid=1) or it went public (I can't remember which) and development has stalled a bit - but now I feel it's time to get things back on track.  So here's the plan. 

### ImageSizer, now.

![](http://uploads.psyked.co.uk/2010/07/imagesizer-screenshot.jpg) ImageSizer is now up to version 0.6.1 - not that the version numbers are anything but arbitrary, of course.  You can import images, rotate them, crop them and resize the lot and output them to your machine.  It works, but the code is a little out of date now, my code-signing certificates are out of date, and I really want to try something new.  So... 

### ImageSizer, future.

Time to create ImageSizer, version 2.  Going for a full re-write on the code side of things means I'm going to try one cool thing - a desktop version and a web-based version.  The reason for the desktop version is obvious, but having a web-based version should make the functionality behind ImageSizer available for people who can't (or don't want to) install the desktop application.  Plus, trial version, and that sort of thing. A newer code-base will also make it easier to build all of the new features into ImageSizer - there's a few suggestions and ideas that never made it to the first version before development slacked off, so those are first on the to-do list.  Things like the long-awaited Twitter and Flickr uploads, and multiple output sizes. So, enough chit-chat. ImageSizer 2 development is underway now, and there should be some more updates on the way. 

### And also...

As my code-signing certificates all went out of date, it makes it a little difficult for the automatic updates to keep everyone up to date.  The application source code is incompatible with the latest version of the Flex SDK, I want to re-architect the application source, and I think that the interface needs a complete re-think to integrate some of the newer application features. Of course, you can still [download ImagesSizer through the AIR Marketplace.](http://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.offering&offeringid=10740&marketplaceid=1)

## Comments

**[Nick](#867 "2010-08-27 14:08:33"):** James, great product, great features, I would definitely be interested in the web version with integrated uploading to a server. Also it wouild be great to see login in there that would allow for diferent output sizes for portait and landscape. For example, we need images with minimum sizes of 900x675 if landscape or 675x900 if portrait. Coud the new version handle that? Very happy to get involved with testing! All the best, Nick

**[Nick](#868 "2010-08-27 14:09:42"):** "login"? err meant to say "a feature" doh

**[James](#869 "2010-08-27 21:32:21"):** The initial web version of ImageSizer 2 is available online @ <http://imagesizer.psyked.co.uk> \- rough and ready at the moment so it may be a little difficult to figure out, but the multiple image output is there - remote upload is still to come.

