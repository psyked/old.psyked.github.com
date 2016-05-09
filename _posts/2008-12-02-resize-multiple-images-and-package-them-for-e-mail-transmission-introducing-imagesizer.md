---
layout: post
title: Resize multiple images and package them for e-mail transmission - introducing ImageSizer!
link: http://www.psyked.co.uk/resize-multiple-images-and-package-them-for-e-mail-transmission-introducing-imagesizer/
author: psyked_james
description: 
post_id: 368
created: 2008/12/02 12:45:30
created_gmt: 2008/12/02 11:45:30
comment_status: open
post_name: resize-multiple-images-and-package-them-for-e-mail-transmission-introducing-imagesizer
status: publish
post_type: post
---

# Resize multiple images and package them for e-mail transmission - introducing ImageSizer!

Or should I say, _finally _introducing ImageSizer.  If you've been here previously in the last couple of weeks, you might have noticed that a couple of links to an ImageSizer application have been floating around.  Back in September (at Flash on the Beach) [Mark](http://www.mmtdigital.co.uk/RVE31d5c7769e694a7cbc286c1c1b2c4fd8,,.aspx), our far-to-clever-for-his-own-good student showed me the inital work on an application he'd been working on for a couple of days - the subtley named ImageSizer. Two months later and I'm finally getting around to implimenting what I offered him then, that we'd post it online and see what people think.  Well, here it is. ![](http://uploads.psyked.co.uk/2008/11/imagesizer1.jpg) You can use the AIR Install Badge to install ImageSizer, or visit the [dedicated ImageSizer page.](/imagesizer-air-application)

ImageSizer, as [Marks' explanation](/imagesizer-air-application) will tell, is an AIR application, designed in Fireworks and built in Flex, and what it does is provides you with a drag-and-drop interface for adding a bunch of Photos, resizing / renaming them, and then outputting them as a .zip file whereever you want.  It was designed for enabling non-techies to take massive images off their multi-megapixel cameras, easily resize and package them for sending via e-mail. What I really liked about the application was Marks' focus on the user interaction - not something that comes easily in an early stage prototype.  For example in the final stage of the zipping process, instead of prompting the user with a browse window to save the zip file, the application presents you with an icon, which you can drag and drop out of the application - so you don't have to work with the annoying folder structures, you can just drop the files onto your desktop, or an open explorer / finder window. The application impliments the AIR Update Framework too, so we could see some more features being added in the future, in Marks' copious amounts of spare time...

## Comments

**[sreekanth](#462 "2008-12-05 08:48:48"):** Hi James, Its a fantastic application.Hope your application solve my Problem. I am facing an issue in my AIR application, when large size images loading its taking to much time and some time system also hang.Is there any possiblity to compress the image while downloading and how can display an image thumb nail.

**[Kishore.v](#463 "2008-12-05 08:58:27"):** Hi James, It is an excellent application Thanks for providing such a beautiful application. I need one help. Currently I am working one Album Project using Flex and AIR. I face one problem while loading larger size images, it taking much time to load and sometimes systems will hangs. The application is working fine while using smaller size images (assuming below 1000 X 1000 pixels). I understand that flash player will support maximum 2880 x 2880 pixels. Is that AIR also will supports the same? Is there any way to compress images at runtime and save the file and load? Please let me know the solution for it and give me the suggestion how to proceed. I am assuming that this will be possible by using ImageSnapshot, JPEG encoder and PNG encoder please let me know my assumption is right or not? Kishore.v

**[James](#464 "2008-12-05 11:46:27"):** Hi Kishore, sreekanth, Take a look at <http://blog.paranoidferret.com/index.php/2007/12/11/flex-tutorial-an-asynchronous-jpeg-encoder/> and <http://www.envrac.org/index.php/2008/06/23/181-reduction-de-bitmapdata-smoothing-pourquoi-c-est-pas-beau-et-comment-ameliorer> \- techniques and classes from both of these links were incorporated into ImageSizer. The first link is an Asyncronous JPEG encoder - useful as a technique as well as a class for dealing with actions that would otherwise cause the application to hang - and the other link discusses an effective way of reducing an images' size for processing. As for the size limit on Bitmaps, it is 2880 x 2880 for individual bitmaps in ActionScript, but that doesn't mean that you can't work with larger ones - I believe there is some technique for cutting the image into manageable chunks, and then stitching them back together afterwards. And the Application is all [Marks](http://www.mmtdigital.co.uk/RVE31d5c7769e694a7cbc286c1c1b2c4fd8,,.aspx) work - I'm just hosting/promoting it!

**[sreekanth](#465 "2008-12-05 13:04:03"):** Hi James, Thaks for your feedback ,the above url's are really helpful for me. Regards Sreekanth K

**[Kishore.v](#466 "2008-12-05 15:27:54"):** Hi James, Thanks for your reply; I have tried the same concept to compress and resize the image. I am getting blank image display. I have written following code, please check once and give me the suggestions. private function saveImage(srcimg:Image,destImgName:String):void{ var byteArray:ByteArray=new ByteArray(); var bmd:BitmapData=new BitmapData(srcimg.width, srcimg.height); var jpg:JPEGEncoder=new JPEGEncoder(60); byteArray=jpg.encode(resizeBitmapData(bmd,1)); var fl:File = File.applicationStorageDirectory; var imgSource:String="d:\thumbnail\"+destImgName; fl = fl.resolvePath(imgSource); var fs:FileStream = new FileStream(); try{ fs.open(fl,FileMode.WRITE); fs.writeBytes(byteArray); fs.close(); }catch(e:Error){ trace(e.message); } } Regards, Kishore.v

**[James](#467 "2008-12-08 10:45:02"):** @Kishore.v: I'll have a look into that - when I get a moment!

**[Simon Peacemaker](#468 "2009-03-04 05:02:47"):** amazing stuff thanx :)

