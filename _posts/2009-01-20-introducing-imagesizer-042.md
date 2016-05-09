---
layout: post
title: Introducing ImageSizer 0.4.2
link: http://www.psyked.co.uk/introducing-imagesizer-042/
author: psyked_james
description: 
post_id: 610
created: 2009/01/20 15:00:05
created_gmt: 2009/01/20 14:00:05
comment_status: open
post_name: introducing-imagesizer-042
status: publish
post_type: post
---

# Introducing ImageSizer 0.4.2

Well, I'm a bit slack on the whole updates front - ImageSizer 0.4.0 and 0.4.1 have already slipped under the radar without a blog post - but with the latest release I thought I'd draw a little attention to it, not least because it fixes a bit an annoying bug that I introduced in version 0.4.1! ![ImageSizer 0.4.2](http://uploads.psyked.co.uk/2009/01/imagesizer042.jpg)

### So, what's new in the latest version?

Well, one of the things that I've found a lot of AIR applications are missing at the moment, is the ability to configure their settings - particulary those things mentioned by Serge Jespers in his post: **"6 AIR features that may annoy your users"** [[link](http://www.webkitchen.be/2008/12/17/best-practices-6-air-features-that-may-annoy-your-users/)].  Back with version 0.3.10 I introduced some Pixel Bender filters to the application.  Version 0.4 introduced the Application Settings window - although it only appeared to work.  Version 0.4.1 expanded on this by introducing some backend code that actually stored the settings, but had a glaring typo that meant the whole thing didn't work.  Version 0.4.2 in short, fixes this. 

### So, what settings have we introduced?

**Remembering window position and dimensions;** **![ImageSizer - Window Preferences](http://uploads.psyked.co.uk/2009/01/imagesizerpreferences.jpg)** **Visual Effects;** **![ImageSizer - Visual Effects](http://uploads.psyked.co.uk/2009/01/imagesizervisualeffects.jpg)** **Automatic Updates;** **![ImageSizer - Automatic Updates](http://uploads.psyked.co.uk/2009/01/imagesizerautomaticupdates.jpg)**

### Download ImageSizer 0.4.2

  

### Known issues:

Unfortunately, no sooner than I'd released this version, I noticed another problem with it.  Or potential problem with it.  I haven't built in any defaults to the application.  So my clever code to enable users to turn off the automatic updates now means that - because there's no settings existing - the automatic updates will be turned off.  Ideally, it should remain turned on!  Darn those logical errors! My next things to explore are **"Start on Login"**, **"System Tray/Dock Icons"** and **"Google Analytics tracking"**.

## Comments

**[Franto](#522 "2009-01-21 11:41:14"):** Wow James, really neat AIR application :) I wanted to make similar in past, but no time :) This really great AIR app...

**[bra](#523 "2009-04-07 12:28:56"):** Hello, The download process doesn't work? Could you help to try your software? Thanks

**[bra](#524 "2009-04-07 12:29:29"):** Hello, The download process doesn't work. Could you help to try your software? Thanks

**[James](#525 "2009-04-07 13:44:10"):** @bra - Do you have the Flash Player or AIR runtime installed, and permissions to install an application on your computer? Have you tried installing the application from the AIR Marketplace? ([http://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.offering&offeringid;=10740&marketplaceid;=1](http://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.offering&offeringid=10740&marketplaceid=1))

