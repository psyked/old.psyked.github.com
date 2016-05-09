---
layout: post
title: Adobe Flash CS3 - off to a worrying start?
link: http://www.psyked.co.uk/adobe-flash-cs3-off-to-a-worrying-start/
author: psyked_james
description: 
post_id: 72
created: 2007/06/20 18:34:46
created_gmt: 2007/06/20 17:34:46
comment_status: open
post_name: adobe-flash-cs3-off-to-a-worrying-start
status: publish
post_type: post
---

# Adobe Flash CS3 - off to a worrying start?

![Adobe Flash CS3 Icon](http://uploads.psyked.co.uk/2007/05/adobe-flash-9.png)I'm afraid I'm only commenting on hearsay here, not actually firsthand experience. Because we still don't have Adobe Studio CS3 at work. Yes I know, a professional "New Media" agency doesn't have the latest and greatest software... shocking. But anyway. People have been conversing / moaning / arguing on FlashCoders mailing list today, about how Flash CS3 weighs in at around 400mb and a 30min+ install time, compared to Flash 8's 110mb and less install time. They're all worried that Flash could end up going down the road of Adobes' Acrobat in terms of file sizes and continual 'updates'. Heck, I use Foxit PDF Reader over Adobe Acrobat now, because every time I start Acrobat (when its' finished loading) it wants to download ~60mb of new updates (Version x.x.x.13) - each one requiring a full system reboot. (One of) Flashs' benifits is the relatively small size for something so unilaterally powerful, and the ease of updates. If Flash turned out akin to Acrobats' bloatware, people wouldn't like it so much, and we'd be in trouble... Come to think of it, Flex isn't too kind on the optimization front. File-size-wise, my own Web-based Induction Training weighs in at 223kb, whereas similar functionality Flex apps are at least 4x that, last time I checked. Ok, it is a completely custom Flash App from the ground-up, but I hoped Flexs' ActionScript 3.0 would be a little more impressive on the download-size front. Apollo / AIR apps are looking good though, let's just hope they stay thata way. Anyway, I'm digressing... Lets hope that it never becomes an issue.

## Comments

**[Jonathan Nicol](#15 "2007-06-27 13:30:42"):** Yeah I installed Flash 9 on my XP laptop last week, expecting it to take just a few minutes. 40 minutes later I was still waiting...! I haven't noticed any impact on the IDE speed or functionality though. Although running CS3 in Vista I do have one issue: when the output window's Filter Level is set to Verbose (ie: trace is turned on) a Flash movie playing back within the IDE will run progressively more slowly. Clearing the output panel will get its framerate back to normal. It makes debugging a pain, and I've taken to setting the Filter Level to None most of the time.

**[James](#16 "2007-06-27 14:20:31"):** Eesh, that does sound frustrating. Director MX2004 does that too.

**[Jonathan Nicol](#17 "2007-06-27 23:53:28"):** > Director MX2004 does that too.

Huh, interesting. I've scoured the net but haven't come across anyone reporting the same issue with Flash CS3. People do seem to have other Vista compatibility problems however. At this early stage in Vista's lifespan, software compatibility issues seem to be par for the course!

**[Jonathan Nicol](#18 "2007-07-02 23:33:07"):** Just thought I'd let you know I fixed that Flash/Vista output window problem. The fix is to locate the Flash executable, and change its compatibility mode to Windows XP SP2 (right click > properties > compatibility). It's a shame such a fix should be required, as CS3 apps are supposed to be Vista compatible.

**[Jonathan Nicol](#19 "2007-07-18 22:37:36"):** Me again... OK, I have fixed the output window problem for good (no compatibility mode hack required). The culprit: My video card (an XFX branded Nvidia 7600 GT). I was already running the latest drivers from the Nvidia website, but discovered that XFX had an even newer version for download from their site. Bingo. I knew Nvidia cards were having some teething issues with Vista, but never imagined it would take this long to sort them out. The road of the early adopter is a long and treacherous one! I realize none of this has anything whatsoever to do with the original topic of your post, so apologies for hijacking the comments!

