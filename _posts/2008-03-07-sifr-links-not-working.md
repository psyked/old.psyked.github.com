---
layout: post
title: sIFR links not working?
link: http://www.psyked.co.uk/sifr-links-not-working/
author: psyked_james
description: 
post_id: 193
created: 2008/03/07 22:30:24
created_gmt: 2008/03/07 21:30:24
comment_status: open
post_name: sifr-links-not-working
status: publish
post_type: post
---

# sIFR links not working?

Here's a funny story. Well, maybe not funny. Or particulary interesting - just informative. Maybe. ![logo_sifr2.gif](http://uploads.psyked.co.uk/2008/03/logo_sifr2.gif)So I'm using sIFR text on a clients' website, which has always worked before - and the links stop working. There's no real consistancy - the links work in Internet Explorer on my computer, but not in Firefox, like they used to. Both browsers use the same security settings, flash versions, javascript versions, but one works and the other doesn't. Other people don't have the links working at all, regardless of the browser - and this seems to only be a problem we noticed recently. Well - a lot of investigating later - I find out that the revised sIFR version 3 works fine in all browsers. New code, or something like that. So we upgrade the code to version 3 (beta 2) and... well, it works - eventually. sIFR 3 is shaping up to be the most comprehensive release yet - but for anyone thinking it'd be easy to upgrade, think again. You're looking at quite a bit of work reconfiguring the javascript to fit the revised model, and the flash files also need republishing - all of which took several hours. Anyway, it's late - but I thought the sIFR 3 project deserved a quick mention. [Find the sIFR 3 Project here.](http://novemberborn.net/sifr3) [Read more about sIFR in general, here. ](http://www.mikeindustries.com/sifr)

## Comments

**[Mark Wubben](#278 "2008-03-08 10:35:28"):** Thanks for the mention! sIFR 2 had an incompatibility with Flash 9,0,115,0, which caused links to stop working. Sounds like this is the issue you ran into. It's been fixed in sIFR 2.0.5. By the way, you should be using r382, rather than the beta. Some issues have been found and resolved.

**[Lorenzo Bolognini](#279 "2009-03-21 19:34:23"):** Hey man, is it not that you had the links inside something with low z-index? That was my issue. L.

