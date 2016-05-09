---
layout: post
title: ActionScript 2 - XML CDATA returns undefined, or htmlText doesn't work!
link: http://www.psyked.co.uk/actionscript-2-xml-cdata-returns-undefined-or-htmltext-doesnt-work/
author: psyked_james
description: 
post_id: 291
created: 2008/09/17 08:40:13
created_gmt: 2008/09/17 07:40:13
comment_status: open
post_name: actionscript-2-xml-cdata-returns-undefined-or-htmltext-doesnt-work
status: publish
post_type: post
---

# ActionScript 2 - XML CDATA returns undefined, or htmlText doesn't work!

### The problem:

Your XML file is fine, it validates as XML.  The file encoding and the xml declaration encoding match.  You can parse the XML, but when you try and put html inside a CDATA element, and then populate a dynamic textbox with it, either your formatting doesn't work (the text still has <b> tags in) or it returns 'undefined'.

### The solution:

This could actually be a twofold problem, and is not helped along by Flash's quirks.  Its most likely that you're either;

  * Accessing the XMLNode incorrectly,

Or

  * Being tripped up by the Flash players' slightly dodgy XML parsing.

### Accessing CDATA correctly

Now, the way that you should be accessing CDATA in Flash is perhaps a little different to what you'd expect.  CDATA should have no effect on how you access your XML - it's a parsing instruction, right?.  Well Flash treats it as part of the XML structure, so if you want to access the data inside the CDATA element, you have to treat the CDATA as a node in itself.  Its actually quite easy though.  Instead of accessing the contents of CDATA with childNode.nodeValue or childNodes, you should be using **childNode.firstChild.nodeValue**.

So childNode is the parent node of the CDATA element, firstChild is the actual CDATA instruction, and nodeValue extracts everything that's inside the CDATA element.

That hopefully, will solve any problems with 'undefined' appearing when you try to access data inside a CDATA element.

### Flash players' dodgy XML parsing?

Yes indeedy, Flash does do things a little different.  CDATA is great because you can put nearly anything inside it, and the XML will still parse correctly.  Whatever's inside your CDATA should not be interpreted by anything else, and won't break anything that tries to read it.

Flash however, still does a little bit of work to it.  If you run a few traces on HTML formatting that you try to send via CDATA, you'll notice that all of the < and > characters are transformed into their encoded versions, &lt; and &gt;. This poses a minor problem because if you just try to whack HTML from your XML into a dynamic textbox, the formatting won't work properly and you'll get the characters < and > appearing, along with the HTML formatting commands - because the < and > characters are encoded.

Annoying yes, easy to fix - yes.

Find and replace is your ally here - or as near as we can easily get;

> xmlcdata**.split('&lt;').join('&gt;').split('>').join('>')**

Run that on your string of text before you put it into your textbox and you're good to go!

### Quirks?

What you also might find is that HTML formatted textboxes could actually display the contents of a CDATA node without the CDATA node being correctly accessed.  If you access the node with the childNodes property, and put that into your textbox, then the contents will display, but not with HTML formatting.

What Flash is actually doing is grabbing the CDATA element (and everything inside it).  Assigning this variable to a textbox _should fail_, but in actual fact it works - to a certain extent.  It seems like the HTML formatting of the textbox allows it to parse the XML element and then consiquently display the content within.  The problem then comes when you want to manipulate this data - the contents of the textboxes' text is not actually a string, but an XMLNode.  Weird, huh?

## Comments

**[Dave](#422 "2008-09-30 20:59:11"):** Thank you for this! I was banging my head against the wall trying to figure out why my text wasn't formatting according to my style sheets and was just coming up as html.

**[srinivas](#423 "2009-01-13 21:10:23"):** Great stuff

**[flysi](#424 "2009-01-14 00:17:00"):** Gaah! Tried your suggestions - using `nodeValue` and running the split/join on my string, but the html formatting is still not showing up in my textfield. I'm kind of at a loss... I guess I'll keep trying, though.

**[James](#425 "2009-01-14 10:24:45"):** Agh, it looks like Wordpress has 'fixed' my code above. You should replace the &lt; and &gt; with < and >. `xmlcdata.split('&lt;').join('<').split('&gt;').join('>')`

**[flysi](#426 "2009-01-15 04:08:37"):** Figured it out. I'm a tool. I had been defining a text format someplace else that was overriding my text definition, and thus resetting my html formatting. Good example that once again reiterates the argument for keeping all your code in one place (as opposed to being sloppy and in a hurry like I was).

**[zrk](#427 "2009-04-21 17:20:39"):** This only half worked on the CDATA I was reading from XML. I had to use the following split/join sequence to get all of the embedded entity codes converted to character data, and thus let the htmltext display properly when loading the CDATA: .split("amp;").join("").split("&lt;").join("<").split("<").join("").split(">").join(">").split("&quot;").join(""").split(""").join(""").split("'").join("'") As an example of an additional problem I was experiencing, Flash was saving the HTML code: "<" as "<". Now it's all happy.

**[zrk](#428 "2009-04-21 17:27:51"):** Wordpress ‘fixed’ my code as well. I'll try again. (Just remove the spaces after the ampersands and before the semicolons): .split("amp ;").join("").split("& amp ;lt ;").join("<").split("& lt ;").join("").split("& gt ;").join(">").split("& amp ;quot ;").join(""").split("& quot ;").join(""").split("& apos ;").join("'") As an example of an additional problem I was experiencing, Flash was saving the HTML code: “<” as “& amp ;lt ;”.

**[Richard lalancette](#429 "2009-06-26 20:19:50"):** Thanks for this article. Saved me quite some trouble :)

**[Robert Taylor](#430 "2009-11-25 16:32:42"):** Thanks for taking the time to write this, and all those who offered their comments. Much saved work! THANKS!

**[Lokesh](#431 "2009-12-02 18:04:21"):** Hi All, Thank you all for useful information on CDATA. I need some help on CDATA; my issue may sound little strange. However, I badly need your response and inputs with this. I am developing a desktop application using Flash, basically a xml based rapid authoring tool. I am using MDM zinc to access the windows api. In this application, I need to save the data that user has created and read it. If user has entered the text something like this - "" while reading the content, I should be able to display the text including the tags. But unfortunately, I am not able to do this in Flash, the CDTAT tags are being removed. Could anybody tell how I can achieve this in Flash. Thanks a lot in advance.

**[greg](#432 "2010-04-28 08:05:58"):** is it not possible to save a sample fla file. i am not that advanced and could follow how to build this in much better if there would be a fla file with sample xml. thanks

**[Rolando](#433 "2010-12-28 01:06:22"):** I've play with this and I can't get it to work. I have done the split after assigning the value of the xml value to a var _html:String, then I have done the replacement and still the stupid TextArea.htmlText can't parse the html code. var _html:String = event.result.detail.specs; _html = _html.split('<').join(''); this.pData.htmlText = _html;

