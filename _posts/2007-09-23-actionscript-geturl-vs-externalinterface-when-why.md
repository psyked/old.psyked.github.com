---
layout: post
title: ActionScript&#58; getURL vs. ExternalInterface - When & Why
link: http://www.psyked.co.uk/actionscript-geturl-vs-externalinterface-when-why/
author: psyked_james
description: 
post_id: 121
created: 2007/09/23 10:37:31
created_gmt: 2007/09/23 09:37:31
comment_status: open
post_name: actionscript-geturl-vs-externalinterface-when-why
status: publish
post_type: post
---

# ActionScript: getURL vs. ExternalInterface - When & Why

This post all stems from a project I've been working on very recently, making a drop-down menu in flash, that sits in a HTML page. _**What we're talking in relation to here is, getting flash to execute JavaScript DOM functions.**_ Now, there are couple of ways for Flash to interact with its host page. The first one that springs to mind is [getURL()](http://livedocs.adobe.com/flash/8/main/wwhelp/wwhimpl/common/html/wwhelp.htm?context=LiveDocs_Parts&file=00001730.html), the same function that enables flash to load webpages. The second requires a little more preparation, and is [ExternalInterface.call()](http://livedocs.adobe.com/flash/8/main/wwhelp/wwhimpl/common/html/wwhelp.htm?context=LiveDocs_Parts&file=00002200.html). Both have an upside and both a downside. One's old-school and one's new-school. There are however, real reasons why you should use one instead of the other in different situations.

### getURL

  * getURL takes advantage of the abilities of your browser. After all, http: isn't the only thing your browser can do. You can (amongst other things) call javascript directly. So, instead of passing a new url through the getURL function, you could pass a javascript function, which would execute on the page. You could, theoretically, pass an entire javascript function as a single string, and execute javascript on your html page - without the function existing in the html.
  * The downside to this is that getURL overrides anything the browser is trying to execute. So, if you've got a stack of javascript functions that are executing, getURL will effectively kill them. - Once flash executes the getURL function, kiss your other functions goodbye.

### ExternalInterface

  * ExternalInterface is an ActionScript 2 'gateway' for JavaScript / ActionScript communication. As well as it's ability for two-way communication, ExternalInterface doesn't kill off other scripts running in the browser.
  * The downside, from a flexibility point-of-view is that ExternalInterface can only call existing functions in either language, it can't create them on the fly. Which is more secure, I suppose.

### So, to summarise:

**getURL:** Kills running scripts, but doesn't need a named function to exist **ExternalInterface:** Doesn't kill running scripts, but does need a named function to exist

## Comments

**[Terry Coatta](#200 "2007-10-12 20:39:10"):** Has anyone had any experience with getting ExternalInferface to work with SWF's that are embedded in PDF documents. ExternalInterface.available returns true, but I haven't found the way to call a function exposed by the addCallback() method.

**[James](#201 "2007-10-13 18:09:06"):** I haven't really had any experience using SWF's in PDF documents. In the ExternalInterface documentation they only ever mention webpages - assumedly because they can run JavaScript. But they do mention that other scripting languages' functions can be called, such as VBScript or even C#. From what I understand, the addCallback() method should execute any named function in the document that hosts the swf file - are you sure that you can execute scripts in this fashion within PDF documents? Perhaps this is a question for the FlashCoders mailing list... Here's a few things I looked into, but I don't think any of them answer your question directly; [Using the ExternalInterface](http://www.peachpit.com/guides/content.aspx?g=flash&seqNum=340&rl=1
) [ExternalInterface.addCallback()](http://livedocs.adobe.com/flash/8/main/wwhelp/wwhimpl/common/html/wwhelp.htm?context=LiveDocs_Parts&file=00002201.html
) [Embedding Flash in PDF files](http://www.adobe.com/designcenter/tutorials/flashpdf/)

**[Terry Coatta](#202 "2007-10-13 21:54:56"):** PDF's have a facility for executing Javascript and I have seen other comments that the ExternalInterface features work from C# and VB when you embed a PDF via an ActiveX control. So, I think the basic capabilities are there. The main issue is how to access the ExternalInterface stuff from the Javascript running in the PDF. We haven't figured out what object to access in order to call the method added via addCallback() for example. Similarly when we try the call() method, it always fails... it's seems like the names of the Javascript functions in the container may be mangled in some way. BTW - We do have fsCommand() working to send information from the SWF to the containing PDF Javascript code. What we really need now is the other direction (to call from the container into the SWF). Terry.

**[James](#203 "2007-10-15 20:44:40"):** Wow. I'm afraid I have no idea on this one... let me know if you make any progress though!

**[James](#204 "2007-10-20 11:37:23"):** It's a long shot, but have you tried using the fully-quallified classnames for the FSCommand / ExternalInterface? I know there's not supposed to be a difference, but I've encountered some issues with Firefox - the ExternalInterface commands not executing unless I used the full flash.external.ExternalInterface.call() - and yet still working fine in Internet Explorer. I wonder if the PDF problems could be something similar?

**[Terry Coatta](#205 "2007-10-20 17:38:43"):** I'll give that a try. Thanks! Terry.

**[Victor S.](#206 "2008-03-17 18:06:16"):** sorry for the bump... u said that "We do have fsCommand() working to send information from the SWF to the containing PDF Javascript code." .... but i cant find any info on this and icant get it to work... can someone give me an example? thanx

**[Terry Coatta](#207 "2008-03-20 23:14:42"):** We just use: fscommand(cmd); in the Flash code. 'cmd' is a line of JavaScript that will be executed by the JavaScript interpreter running within the PDF document. If you have defined JavaScript functions in hte document, you should be able to call them. Terry.

**[me](#208 "2008-08-20 10:47:55"):** Hi, A bit of a late reaction but in your article you state that ExternalInterface does need a named function to exist. This is a common misconception, as explained in [.

**[James](#209 "2008-08-20 11:12:29"):** @me - that JavaScript injection article (<http://www.actionscript.org/resources/articles/745/2/JavaScript-and-VBScript-Injection-in-ActionScript-3/Page2.html>) is quite interesting - and a neat hack, which could prove useful in certain situations...

**[dmitry](#210 "2009-02-21 02:29:04"):** THANK YOU SO MUCH JAMES! flash.external.ExternalInterface.call("alert", "ALERT");

**[jeff](#211 "2009-09-14 18:55:30"):** Hello- James, thank you for the insight into the ExternalInterface function. I am trying to get actionscript to communicate w/ javascript. The situation is: I have an aspx page, w/ a login and password at the top and a flash movie as the main active area. When user clicks on a btn in the main area, I need to call javascript from flash to check if user is logged in already or the id and password are valid. From what I know to keep it on the client-side, ExternalInterface is the best option. I thought using this w/in a btn to receive a value through a string, then based on the value returned have an if/else conditional to navigate to the proper frame label...either please login with your username and password, or grant access and go to the appropriate frame. Could you help fill in the blanks? Thanks..... -Jeff

**[Brad](#212 "2010-06-08 18:38:38"):** Hi James, I know it's an old article, but great stuff. Have you tried calling getURL from flash (or Captivate, etc) inside a ConnectPro environment to make JS calls? I have a function working great in Firefox and Chrome, but the function does not fire in Internet Explorer. As usual trying to make things work in IE is 80% of my work :). Any ideas?

