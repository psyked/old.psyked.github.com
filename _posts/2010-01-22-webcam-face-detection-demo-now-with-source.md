---
layout: post
title: Webcam Face detection demo&#58; Now with source!
link: http://www.psyked.co.uk/webcam-face-detection-demo-now-with-source/
author: psyked_james
description: 
post_id: 1141
created: 2010/01/22 09:07:43
created_gmt: 2010/01/22 08:07:43
comment_status: open
post_name: webcam-face-detection-demo-now-with-source
status: publish
post_type: post
---

# Webcam Face detection demo: Now with source!

So a little while ago, Halloween in fact, I threw together a demo of some face-detection stuff I'd been looking at. [[Check out the original post here.](/adobe/flash/webcam-face-detection-spooky-goings-on.htm)]  We originally had the demo on the MMT Digital homepage, but recently that's been updated and my demo got lost in the process, so I've restored it here, along with the Flex project for it. ![Augmented Reality Halloween](http://uploads.psyked.co.uk/2009/10/halloween.jpg) So, here it is: the live demo and underneath, a link to the source code for it. [kml_flashembed movie="http://uploads.psyked.co.uk/2010/01/FaceDetector_Camera.swf" height="375" width="500" /] The code itself I'm not going to try explaining, but it's a hack of other demos that are out there on the web. 

## [Download the Flex project now.](http://uploads.psyked.co.uk/2010/01/TrickOrTweet.zip)

## Comments

**[james](#785 "2010-06-07 07:29:59"):** hi. I can't see nothing in the example and flex project. I check the configuration but still the same. can you help me?

**[James](#786 "2010-06-07 18:41:58"):** @james - Can't see anything as in camera feed? If you're on a Mac it might be that this example has out-of-date camera detection - Macs tend to get confused with cameras in Flash, and the code might be only picking the first camera in the available cameras list. I shall try getting the code on GitHub and seeing if there's a fix to be made...

**[james](#787 "2010-06-13 03:03:06"):** hi thanks for your attention, but my operating system is Windows 7. The strangest thing is that I does not like in your site, but if it works to a friend.

**[James](#788 "2010-06-14 22:14:02"):** @james - Not sure what's up there then!

**[kacrut](#789 "2011-03-25 09:39:29"):** can this marilena work with XML data? How?

**[Norman](#790 "2012-02-21 01:17:18"):** Hi. I would like to use your code for make a change with the mask, but I don´t know how to open the file....which is the program I have to get to modify your project??? I use Flash Cs 5 but I think it isnt the correct program

**[James](#791 "2012-02-21 10:04:59"):** The project is originally a Flex Builder project file (now Flash Builder). You should be able to extract the contents from Zip format to access the code, however.

**[Norman](#792 "2012-02-22 20:11:34"):** Thaks a lot! But when I import the project the program show me thsi message "Application "src/WebcamFaceDetector.as" does not exist. It might have been deleted." what does it means. Is it incomplete the project??? Pleeeease help I need to run that project

**[Norman](#793 "2012-02-22 22:25:06"):** Finally I can edit the MASK but now I have another doubt. How can I put an kind of ANIMATED MASK like a GIF. I already made tests with gifts but it only appears the first image. not the secuence.

**[James](#794 "2012-02-23 10:02:41"):** Unfortunately, the default Flash components only support non-animated GIF images, which is why it isn't playing. You could replace the Image class with ByteArray.org's AS3GIF class (http://code.google.com/p/as3gif/) however, which does add support for animated images.

**[Norman](#795 "2012-02-23 13:48:51"):** Could you make the change please? and send me or post the modify project? Pleeease. If you want, I could pay for the work... Apology for the inconvenience = )

**[Louis](#796 "2012-03-12 04:08:13"):** @James, I'm wondering whether it's possible to detect multi-face with your facial recognition function?

**[Louis](#797 "2012-03-12 04:08:34"):** @James, I'm wondering whether it's possible to detect multi-face with your facial recognition function?

**[James](#798 "2012-03-12 10:13:30"):** @Louis It's definitely possible - it might even be supported at the moment, or it's easy to add. Certainly some of the early prototypes had that functionality in there as standard - you just have to tweak the code that evaluates face matches and face dimensions, when you're working with a wider camera angle.

**[Karolina](#799 "2012-04-06 06:22:28"):** Hi James, This may seem like a far stretch, but would you know how to start/stop music based on facial detection?

**[Edinei](#800 "2012-09-13 20:34:37"):** Hi James, i`m the same problem of @Norman the program show me this message “Application “src/WebcamFaceDetector.as” does not exist. Can you help me, please? Thanks

**[sravan](#801 "2013-03-22 16:50:26"):** Hi Can u send snapshot code for this Webcam Face detection demo: Now with source!

**[cfnm](#802 "2013-05-21 09:52:32"):** I always spent my half an hour to read this webpage's articles or reviews every day along with a mug of coffee.

