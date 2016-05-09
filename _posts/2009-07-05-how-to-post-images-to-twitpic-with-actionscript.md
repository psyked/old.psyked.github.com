---
layout: post
title: How to: Post images to TwitPic with Actionscript
link: http://www.psyked.co.uk/how-to-post-images-to-twitpic-with-actionscript/
author: psyked_james
description: 
post_id: 926
created: 2009/07/05 21:22:23
created_gmt: 2009/07/05 20:22:23
comment_status: open
post_name: how-to-post-images-to-twitpic-with-actionscript
status: publish
post_type: post
---

# How to: Post images to TwitPic with Actionscript

Uploading images to services like [TwitPic](http://twitpic.com/) is actually as easy as sending a HTTP POST request, which means its also pretty darned simple to upload something from Flash Player 10 or AIR. This is an example for AIR, but doing something similar in Flash Player 10 should also be possible - you just need to swap the references to the File class to FileReference. ![TwitPic](http://uploads.psyked.co.uk/2009/07/twitpic.jpg) So, how do we get our photos on TwitPic?  Well, let's check the API: [TwitPic API](http://twitpic.com/api.do). According to the API, it's just a case of posting an image file with additional parameters of **username**, **password** and if you like, **message**. And the upload location is pretty simple too - _http://twitpic.com/api/upload_ or _http://twitpic.com/api/uploadAndPost_. One for just uploading, and the other for posting things to your twitter feed at the same time. If you're posting automatically to twitter, TwitPic will automatically add the url to your image to the start of your tweet. So, let's check out some basic code: 

### The code:

[sourcecode language='javascript'] var urlVars:URLVariables = new URLVariables(); urlVars.username = "username"; urlVars.password = "password"; var urlRequest:URLRequest = new URLRequest("http://twitpic.com/api/upload"); urlRequest.method = URLRequestMethod.POST; urlRequest.data = urlVars; var file:File = File.desktopDirectory.resolvePath("test.jpg"); file.upload(urlRequest, 'media'); [/sourcecode] In a nutshell, that code will upload an image file (called "test.jpg") from the desktop, to TwitPic. We create an URLVariables object (which contains the additional parameters required for the POST request), create an URLRequest object with the target http request, set the method, assign the URLVariables to the URLRequest, and then finally grab a reference to our file and call the upload method on the file, passing in the URLRequest. Ok, URLVariables and URLRequests are simple enough - but the thing that was difficult for me to get my head around was the **file.upload()** method. What it actually does is convert the File (or FileReference) to binary data, and sends that as an additional URLVariable in the URLRequest.  The first parameter it takes is an URLRequest, and the second is the name of the variable that the binary data is assigned to.  I'd kinda assumed that a single URLVariables object would contain all of the data you're sending in your request, but when you're using the File.upload method, it seems to be compositing a new set of variables from the method and the URLRequests' existing data.  Confusing, to start with.

## Comments

**[Gritfish](#657 "2009-07-06 00:15:20"):** You can also do it without the AIR stuff if you get corelib (available from Adobe labs, I think... also try google code). It lets you convert any movieclip/image/bitmapdata in flash to jpg or png binary data, and send it as a URLVariable.

**[James](#658 "2009-07-07 08:38:28"):** Gritfish - That's very good to know - good info.

**[isantos](#659 "2009-08-13 18:40:07"):** hi… thanks for the info but I want put the code on Flex with FileReferense but appears an error: “Error #2044: SecurityErrorEvent no controlado: text=Error #2049: Violación de la seguridad Sandbox: http://www.ddsmedia.net/tweet/index.swf no puede cargar datos en http://twitpic.com/api/uploadAndPost.” i try with localhost and on server online can you help me??? please

**[James](#660 "2009-08-15 21:52:12"):** @isantos - I think you need to get a crossdomain.xml file setup on your ddsmedia.net domain - one that allows data loading from external subdomains. That should hopefully sort the issues out.

**[isantos](#661 "2009-08-18 19:51:51"):** thanks for response.... what is the content of the crossdomain.xml file??? actually i have a file but i not sure if the contect is the correct... can you help me??

**[isantos](#662 "2009-08-27 22:50:45"):** hey James... i need you help... i have a crossdomain.xml file in the server but isn't work the flex application.... my file contains the follow lines where is the error?? .... please help me...

**[isantos](#663 "2009-08-27 22:53:04"):** sorry, i don't post the content file... :D <?xml version="1.0" encoding="utf-8"?> <cross-domain-policy> <site-control permitted-cross-domain-policies="all"/> <allow-access-from domain="*"/> <allow-access-from domain="*" secure="false"/> <allow-access-from domain="*" to-ports="*"/> <allow-http-request-headers-from domain="*" headers="*" secure="false"/> </cross-domain-policy>

**[James](#664 "2009-09-02 08:20:33"):** isantos - One thing to try might be setting the namespaces of your crossdomain file, try replacing the <cross-domain-policy> node with; <cross-domain-policy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="http://www.adobe.com/xml/schemas/PolicyFile.xsd">

**[James](#665 "2009-09-02 08:23:33"):** The best way to figure out the error is to run in debug mode, and see what kind of security errors you come across.

**[shammi](#666 "2010-07-04 17:05:57"):** hi do u think if i add urlVars.media= UploadPostHelper.getPostData( 'image.jpg', byteArray ); and then var loader :URLLoader = new URLLoader() loader.load(urlRequest); it will work. ? please help. i want to use it in a web application. so i cannot file or filereference class. thanks for your help.

**[James](#667 "2010-07-07 23:35:32"):** @shammi - If you're using Flash Player 10 then you should be able to work with the FileReference classes - just not the File classes. I haven't tried sending a ByteArray as part of the POST data from Flash, but I should think you could get it working - I just don't know what the exact code would be.

**[tom](#668 "2011-02-09 15:00:48"):** thanks for sharing but it's not working. do i just need to copy and paste the code? would you be so kind to provide a working example? thanks

**[James](#669 "2011-02-10 10:30:04"):** It's quite possible that this just doesn't work anymore, because twitpic have had to update their API to use OAuth 2. - I'm not exactly sure. What kind of error messages did you get?

**[vincent](#670 "2011-02-11 11:01:09"):** any chance for a tutorial how to use it without AIR? i'ld love to use it in a free online project. (based on flash player 10.1) what part do i need to change in your code? cheers

**[CraigG](#672 "2012-04-10 09:58:57"):** Just started using as3. Im trying to save an image to twitpic after flash takes one and encodes from the webcam. At the moment it saves to my desktop using adobe air. How would i build this into a function. going to seem like a stupid question but im not familiar with as3 yet. just want it to come after the image has been take so it saves straight to twitpic.

