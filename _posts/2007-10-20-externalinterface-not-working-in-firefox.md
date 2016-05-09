---
layout: post
title: ExternalInterface not working in Firefox?
link: http://www.psyked.co.uk/externalinterface-not-working-in-firefox/
author: psyked_james
description: 
post_id: 132
created: 2007/10/20 11:31:39
created_gmt: 2007/10/20 10:31:39
comment_status: open
post_name: externalinterface-not-working-in-firefox
status: publish
post_type: post
---

# ExternalInterface not working in Firefox?

Here's a wierd one. Let's say you have a flash navigation - one of those old DHTML style drop-down ones, but done in flash and layered over the top of your page content. You can stick the wmode to transparent and have a transparent background for your flash. That's dandy - but in most browsers (ie. firefox) you'll run into problems interacting with the content underneath your flash movie, particulary hyperlinks. Hyperlinks and form fields just become inaccessible. Setting the wmode might make things transparent, but it doesn't help the 'click-through' aspect of transparency. So, what do you do? The solution I've been using is a JavaScript function which resizes the flash movie, activated using ExternalInterface.

### The problem?

### 

In Internet Explorer, it works fine. JavaScript calls, DOM elements resize. Firefox? No dice. 

### The solution.

### 

The solution I found has prettymuch baffled me as to why it should work, but it does. Using the fully-qualified class name for ExternalInterface (`flash.external.ExternalInterface`) solved all of my Firefox woes. So quite simply - change your `ExternalInterface.call();` to `flash.external.ExternalInterface.call();`

## Comments

**[Tom](#225 "2008-01-18 20:21:03"):** Oh thank you, that was really, really annoying. It appears to be file-specific, I use ExternalInterface all the time, even have an updated 'traceLog' class that automatically adds extended info and traces to both regular trace and Firebug's console.log() in Firefox, and in this ONE file no matter what I did ExternalInterface would not work. All of my other files worked fine, even ones using the same exact class file (added to my main AS2 classpath). Could be something to do with the fact that this FLA was created on a Mac and published on a PC? Not likely but who knows... that's the only difference I can think of between all of my working files and this one.

**[James](#226 "2008-01-19 17:39:33"):** I wouldn't've thought it could be a Mac / PC issue, both of the files that caused me hassle were created and published on a PC. We have had separate issue with flash MovieClip loaders failing, apparently due to the hosting server being unix-based. I wonder if that has any effect on ExternalInterface?

**[Green](#227 "2008-10-15 22:54:34"):** Why the heck does this not work? Would this not be a workaround for the popup blockers. `myClip.addEventListener(MouseEvent.CLICK, myButtonFunctionWOW); function myButtonFunctionWOW(event: MouseEvent) { flash.external.ExternalInterface.call("http://www.site.com/index.html","_blank",'height=600, width=200'); }`

**[James](#228 "2008-10-16 10:21:37"):** Green - the ExternalInterface has to call an existing function in the page - I see what you're trying to do, but you're doing it wrong! The 1st variable of the call has to be the function name, and the next are the variables, I think. So what you're trying to do is call a function named 'http://www.site..' which doesn't exist. You need to call a function that creates a new javascript window, and pass the url and target as variables to that. [Have a look at this page.](http://www.psyked.co.uk/actionscript/actionscript-geturl-vs-externalinterface-when-why.htm)

**[Robert](#229 "2009-02-02 15:52:25"):** Wow.. you just saved me a heap of trouble.. thanks!.. Does beg the question of WHY.. but then actionscript 2.0 always was quirky.. Will be glad when all my work gets onto 3.0 thanks again

**[Ed](#230 "2009-02-09 03:30:40"):** Thanks. This works perfectly!

**[Aubrey](#231 "2009-03-13 07:57:38"):** I just want to confirm that this solution works. This is great, I always wondered why External Interface failed in AS2. Coincidentally you do not need to implement this for it to form from AS3, thanks Adobe. ;) My client thanks you, and so do I! -aubz

**[Viktor](#232 "2009-03-19 14:52:03"):** thanks man, it works

**[Dave](#233 "2009-05-23 11:14:14"):** Doesn't work for me unfortunately... Doing flash.external.ExternalInterface.call("alert", "WTF?") still does nothing. :(

**[James](#234 "2009-05-25 22:57:17"):** @Dave - have you tried creating your own javascript function in the HTML page? I'm not sure if you could call 'native' javascript methods via ExternalInterface - but maybe you could make your own wrapper function in javascript that would do the same thing. [This link might help.](http://www.actionscript.org/resources/articles/745/2/JavaScript-and-VBScript-Injection-in-ActionScript-3/Page2.html)

**[aw](#235 "2009-06-22 09:09:40"):** It's able to call native functions. you may even call console.log if you have firebug enabled :)

**[Nathan](#236 "2009-07-01 20:05:01"):** Just tried the FF fix and I still am getting no dice with FF 3.5. Have you tried this is the latest FireFox 3.5?

**[Superficial](#237 "2009-09-04 15:02:39"):** After also having these problems with FF 3.5 i found out what was wrong in my case. When i inspected the DOM i saw that in FF using the (Adobe preffered) way of getting a pointer to the Flashfile, document[flashid] returns a NodeList when using the Prototype framework. This nodeList contains 2 nodes, the embed and the object tags with the id=FlashId and name=FlashName. I worked arround this "problem" by checking if the value that's returned by document[FlashId] has a length attribute and when it does, take the 2nd element of that array to work with. This seems to work in the most popular browsers. Tested it in IE, FF, Chrome, Safari (PC version) and Opera Hope this helps anyone with the same problem. Greetz Superficial

**[Jon](#238 "2009-09-07 00:47:21"):** Hello could you Superficial could you expand on your solution for the lest technically minded? thanks Jon

**[Corona](#239 "2009-09-15 11:57:47"):** @Superficial You mean on the lines of this? http://corona.pastebin.com/m29c2a5e5

**[Corona](#240 "2009-09-15 11:58:42"):** srry wrong link EDIT: http://corona.pastebin.com/d4d25a0d1

**[Robson Waterkemper](#241 "2009-12-08 15:57:48"):** I was having problems with ExternalInterface and Firefox and Chrome and discovered that the Adobe Script was not writing the Flash tag quickly enough, so when the browser tried to find the addCallback() function it was not there at the time. Simply putting my Javascript function that calls the Flash created addCallback() in a window.setTimeout() calling solves the problem. Delays less than 200 ms still make the problem to occur. I didn't have to use the solution of trying to find if the "length" attribute exists in the document[FlashId] object. Just calling "FlashEmbed = document[FlashId]" worked just fine.

**[James](#242 "2009-12-08 16:48:05"):** Thanks for the tip, Robson - hopefully will prove useful to someone!

**[Suraj Chandran](#243 "2010-04-01 06:35:49"):** I cant thank you enough. I spend hours trying to figure what the fuck is wrong. And using the fully qqualified names solves it. I still wonder why this solves the problem.

**[sean](#244 "2010-04-30 20:39:12"):** No man this did NOT work. Thank you though for trying, I wish it were this simple.

**[Fiona Coulter](#245 "2010-11-11 00:11:46"):** Thanks Robson WaterKemper, the window.setTimeout() solved the problem for me. I thought that it would be on the right track because the javascript error console kept telling me that the callback function within Flash was not a function, so clearly it is not being defined quickly enough.

**[Jason](#246 "2010-11-20 14:57:59"):** My trouble is very strange. It's always OK in IE. but it's not OK in Firefox, when I just make the HTML file larger by adding some text in the html code.

**[Rachael](#247 "2011-07-15 15:06:51"):** Hi! This is happening currently for Firefox 5.0. I'm imprinting "flash.external.ExternalInterface" and these are my functions: `//confirmation dialog function confirmationDialog(mesg:String) { return flash.external.ExternalInterface.call("confirm", mesg); } //alert dialog function alertDialog(mesg) { return flash.external.ExternalInterface.call("alert", mesg); } ` I'm using Actionscript 2.0 in Multimedia Flash Professional 8. Confirmations and alerts will crash in Firefox for a while, then it will be okay and work perfectly for a few hours. I haven't experienced any problems with IE9 or Chrome. Any help would be MUCH appreciated, thanks!

**[James](#248 "2011-07-20 08:31:04"):** @Rachael - I've found that when you're trying to launch popup windows or confirmation windows in the external page JavaScript, it doesn't work so well if you try to immediately launch the popup in response to a click in Flash. I've worked around this in the past by adding the click into an ActionScript Timeout, using code like: `function alertDialog(mesg) { setTimeout(function() { flash.external.ExternalInterface.call("alert", mesg); }, 0); }`

**[Rachael](#249 "2011-07-20 15:34:26"):** Thanks James! I tried that and it didn't work..it said that there is no method with the name setTimeout. After digging around the internet, I found out that changing it to _global.setTimeout would help. So it compiled fine, but it is still crashing in FireFox, so it didn't solve the problem.

**[Venkat](#251 "2012-03-28 13:20:28"):** i tried, IE work fine. but not working firefox and chrome. var pageURL:String = fash.external.ExternalInterface.call("window.location.href.toString"); if(pageURL == null){ pageMsg.text = "Seems like javascript is disabled"; }else { pageMsg.text = "Enabled"; }

**[sxr5](#252 "2013-05-28 05:03:32"):** @James sorry to trouble,my english is poor. i found in firefox the flash Script was not writing the Flash tag quickly enough, so when the browser tried to find the addCallback() function it was not there at the time,but in ie and other brower it 's fine. I don't know why,if you found the solution ,please tell me why

**[sxr5](#253 "2013-05-28 07:11:55"):** I try it again ,all browers need to waiting for a second. $(document).ready just can't load the method immediately;

