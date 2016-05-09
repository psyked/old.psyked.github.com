---
layout: post
title: ImageSizer updated, and now with a Crop tool.
link: http://www.psyked.co.uk/imagesizer-updated-and-now-with-a-crop-tool/
author: psyked_james
description: 
post_id: 801
created: 2009/03/15 17:28:50
created_gmt: 2009/03/15 16:28:50
comment_status: open
post_name: imagesizer-updated-and-now-with-a-crop-tool
status: publish
post_type: post
---

# ImageSizer updated, and now with a Crop tool.

ImageSizer is now up to version 0.4.6.  If you're paying attention to the number of updates I've been putting up here, that's a noticable jump from the last update, so I guess it's time for a roundup of all of the features that have been introduced in this, and the other recent updates I forgot to mention.   If you've been running ImageSizer then hopefully you'll have seen the automatic updates announce themselves, but here they are with a features list and pictures! 

## General updates:

![ImageSizer version 0.4.6](http://uploads.psyked.co.uk/2009/03/imagesizer_main.jpg) The first thing you'll notice is that the interface is looking a little bit brighter - with those helpful #1, #2, #3 markers. They're designed to make it easier to identify the process you need to take to use the application.  We've also added more instructions to the application, in a simpler language (hopefully). ![ImageSizer - encoding screen](http://uploads.psyked.co.uk/2009/03/imagesizer_encoding.jpg) **The encoding screen:** It's only a visual thing, but it looks nice.  You can now see a preview of the image that's being processed, as well as the individual image progress and the overall batch progress while the application is working.   Technically, this whole process has also been rewritten.  In the original version the processed files were stored in memory, which wasn't too great because it meant that if you were working on a lot of images it would really hog your system resources and actually slow down the resampling process. This has been changed now to take advantage of the file system more, and you shouldn't notice an ever-increasing drain on your system resources, and the process shouldn't slow down. ![ImageSizer output screen.](http://uploads.psyked.co.uk/2009/03/imagesizer_output.jpg) **The output screen: ** Again with the visual and textual overhaul. We're still working on the drag-and-drop method of working with the file system, but there's a new option - you can export your batch of images as a single folder or a compressed zip archive. It also makes more sense to set your output filename on this screen, so we've moved it here (it used to be on the first screen). So, that's the changes to the existing screens - what about this 'Crop tool' you mentioned? 

### The Crop tool.

![ImageSizer Crop tool](http://uploads.psyked.co.uk/2009/03/imagesizer_crop_tool.jpg) As often as you want to resize images, you find you also want to cut just that little bit off the image. Well now you can, with the built-in Crop tool. From the inital screen, just click the crop button next to the image name, and a new window will open.  Click and drag the handles in the four corners to select the area of the image you want to crop to, and click the 'Crop Image' button.  Could it be any easier? The crop tool functionality is aided by the awesome [Flex Image Cropping Component](http://blog.mediablur.com/2008/02/20/flex-image-cropping-component/) from Random Madness. 

### Future developments.

There's a lot of other things that are planned, such as Twitter and Flickr uploading, JPEG file metadata editing, an image enhancing tool, and a few clever tricks we've thought of on the performance / ui front. And then there's fixing any bugs or memory leaks that we find! If you have any suggestions or spot a bug, then add a comment, or send us a message. You can also follow the official development microblog on Twitter: [@ImageSizer](http://twitter.com/ImageSizer). You can use the AIR Installer badge in the column to the right of this post, or [download ImageSizer via the AIR Marketplace](http://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.offering&offeringid=10740&marketplaceid=1).

## Comments

**[Doubleslash](#572 "2009-03-15 19:03:21"):** This looks awesome! What kind of skin you are using? Looks like Kingnare from scaleninegrid or the skin the Adobe Media Player is using?

**[James](#573 "2009-03-15 20:25:06"):** I'm pleased you think so. The skin is actually one that we've created from scratch - it's loosely based around the Adobe Media Player styling, but it's all a clever combination of fills, border colours and custom skins from a Flash SWC. I've actually just started using [Degrafa](http://www.degrafa.org/) to replace the existing skins, as another of the future developments will be introducing custom skins.

**[lemoussel](#574 "2009-03-24 10:35:19"):** Hi, Excellent tool ! When a french translation ? If you wish it, I can help you in the translation in French.

**[Al](#575 "2009-03-25 11:39:08"):** Lol, just installed this from the "badge" on the site and then as soon as I run it, AIR says there's an update. You may wish to amend that. I haven't had a play yet (it wanted to update) but looks good. Came across this from WRD btw (<http://www.webresourcesdepot.com/16-fresh-adobe-air-applications-for-designers-developers/>).

**[James](#576 "2009-03-25 11:48:30"):** @Al - The badges on the site, and on the Adobe Marketplace should be the most up to date. - I'll have to check that out. Let me know what you think of ImageSizer - you can always use the integrated Feedback form in the application!

**[Adam](#577 "2009-03-31 23:39:56"):** This is an awesome little program and is exactly what I was looking for. The only thing that it's lacking that I was looking for is a rotate function. Any chance of that coming in a future release?

**[James](#578 "2009-03-31 23:49:03"):** @Adam - Thanks for the feedback, a rotate function is on the to-do list. We're working on the next version, which isn't due to include a rotate function, but I'll bump it up the list and try and have that function in the next couple of releases!

**[sudeep](#579 "2009-04-02 05:49:35"):** Yeah!! its great. I always use the third party softwares. Now would like to try this. thanks

**[Michael](#580 "2009-04-09 23:31:42"):** Great tool. My wish for a future version would be the ability to add a png, gif or jpg as a watermark to the resized images.

**[tobyct](#581 "2009-04-25 13:15:06"):** Very nice app. I did use irfanview for bulk resize but this is much simpler, and provides better results. It also looks good. Highly recommended.

**[anna](#582 "2009-06-30 17:35:43"):** we´re having problems - downloaded this, it worked once, but now won´t open - is it ok on windows xp? thanks

**[James](#583 "2009-06-30 21:32:26"):** @anna - Sorry about that. ImageSizer 0.4.12 has had some issues - the installation directory was changed and this caused some installations to crash. A fixed version of ImageSizer is available now (version 0.4.12.1) but you'll have to download and install it manually again. (from [the AIR Marketplace](http://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.offering&offeringid=10740&marketplaceid=1).

**[Steven](#584 "2009-07-13 16:36:55"):** Hi James - I just downloaded for my Mac. Can't seem to get the main screen to open after the install. It does open, but there's no main desktop or application window. Perhaps I'm doing something wrong?

**[James](#585 "2009-07-15 00:44:57"):** @Steven - there's been some issues with the most recent versions of ImageSizer. Hopefully the most recent versions of (0.4.12.1 / 0.4.12.2) will fix those issues, but if they don't then uninstalling / reinstalling ImageSizer seems to do the trick.

**[Daniel](#586 "2009-07-22 17:52:44"):** Hi James. I have the same problem as Steven, in two different computers both with xp and Adobe Air 1.5.1. After install the application run, and take processor and memory, but I can't see any screen of it. The installed version is 0.4.12.2, and I tried to uninstall and reinstall (Imagesizer and Adobe Air) and same. I hope you can fix it, seems to be a very interesting app :-)

**[Elizabeth Richardson](#587 "2009-07-23 03:37:06"):** I'm having the same trouble as Steven also....and like Daniel, I have tried uninstall and reinstall to no avail. Hope it's an easy fix. We loved image sizer.

**[James](#588 "2009-07-23 09:50:56"):** Daniel, Elizabeth Richardson - I've just tested ImageSizer on another machine, and found some more quirks(!) It seems that version 0.4.12.2 doesn't contain some of the source files for the application, which oddly enough stops the main window from loading. ImageSizer does however open 'in the background' and you get a System Tray Icon appear. I've managed to open ImageSizer by using the right-click menu on the System Tray Icon, and clicking 'Show ImageSizer'. I will try and get a fixed version of ImageSizer out soon. Anyone would think I didn't test things (I do, I swear!)

**[Mark](#589 "2009-07-24 09:40:32"):** Hi James, just downloaded from Adobe (04123) and from Psyked (0.4.91?) - failed to display. Seems to run, no icon tray icon though. Can only cancel it via Task Manager. System Win XP SP3 Mark

**[Mark](#590 "2009-07-24 09:52:21"):** Retract my last - found an extra instance running in Task manager - turned that off and the app runs. Which is the most recent version though?? Confused by the update available message! Mark

**[Palak Patel](#591 "2009-08-25 22:18:19"):** Hey James:- let me know software or application which I can use for resize my pic in to my mobile display size like 240X320.. I am urgently in need of this type of softwatre/application.

**[djl281755911](#592 "2009-09-18 06:38:40"):** so cool effect

**[John Swaringen](#593 "2009-09-29 05:06:09"):** James, I have something weird going on with my PC where I can't run the flash download app properly. Is there a link to the .air file on Adobe that you can give me?

**[James](#594 "2009-09-29 10:46:01"):** Sure, the latest link is http://www.psyked.co.uk/airapps/ImageSizer0522m.air

**[tobyct](#595 "2010-02-27 00:35:21"):** Known issues with windows 7? Prefer this adobe app to others out there but just installed Windows 7 and am in the process of reinstalling my fav apps and am having issues with this. Would hate to go else where.

**[James](#596 "2010-02-27 00:44:45"):** There's no particular known issue with Windows 7 - it certainly works on a every machine I've tried it on. What issue are you getting? Problems installing, problems running it?

**[tobyct](#597 "2010-03-06 11:45:36"):** Hi James, It was hanging on splash screen. It is now working fine though. Great little app, thanks.

**[kkdhf](#598 "2010-06-10 07:16:25"):** hi James, can u send a copy about The crop tool to me? i can't visit Random Madness's home page. thx a lot .. my email: kkdhf@1263com thx again.

**[James](#599 "2010-06-14 22:12:22"):** kkdhf - I've uploaded a copy of the image cropping component to GitHub: http://github.com/psyked/Flex-Image-Cropping-Component

