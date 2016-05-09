---
layout: post
title: AIR files downloading as .zips?
link: http://www.psyked.co.uk/air-files-downloading-as-zips/
author: psyked_james
description: 
post_id: 211
created: 2008/04/11 22:19:05
created_gmt: 2008/04/11 21:19:05
comment_status: open
post_name: air-files-downloading-as-zips
status: publish
post_type: post
---

# AIR files downloading as .zips?

Well, here's a mercifully easy to solve problem with Adobe AIR. A couple of people pointed out that Internet Explorer was saving my .air download files as .zip format - even going so far as to change the filename extension to .zip. (Firefox is fine, and doesn't do this.) AIR packages are based on the Zip format, so the file contents itself aren't actually being changed - but when the end user recieves the file, this is going to change the application that handles the file on their local machine.  In the case of Windows, the file explorer will extract the archive, and the user will be looking at a bunch of useless folders and compiled source files. Without the .air extension, or the .air resource forks, then the installation process for your shiny new AIR App. just isn't going to start. Given that .air files are based on zip archives, it isn't too much of a mystery to see where the .zip associations come from, but I never thought that IE would go sofar as to rename files for you! Well, the problem here is server mime-types[[1]](http://en.wikipedia.org/wiki/Internet_media_type) \- file associations that the webserver uses to decide how to deliver content. I've encountered a similar issue with .flv (Flash Video) files before - and here we are again. What you need to do is completely server-side, and get the mime-type "`application/vnd.adobe.air-application-installer-package+zip`" associated with .air files. 

## Read the official notes;

  * [AIR:Release Notes - Setting the MIME type](http://labs.adobe.com/wiki/index.php/AIR:Release_Notes#Setting_the_MIME_type_on_your_Web_server_for_AIR_applications)

## Comments

**[Luveen](#306 "2009-05-05 21:20:01"):** Thanks so much for this post! I'd developed an file viewer AIR app for download from my company's web app, and it strangely kept renaming the file to .zip. This really makes things much easier to solve. Thanks once again!

**[Giulio](#307 "2010-10-31 10:10:17"):** Many thanks for your advice. Is very useful!

