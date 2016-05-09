---
layout: post
title: (Flash/Javascript) problems in a .Net Content-Managed Website
link: http://www.psyked.co.uk/flashjavascript-problems-in-a-net-content-managed-website/
author: psyked_james
description: 
post_id: 247
created: 2008/06/08 13:53:13
created_gmt: 2008/06/08 12:53:13
comment_status: open
post_name: flashjavascript-problems-in-a-net-content-managed-website
status: publish
post_type: post
---

# (Flash/Javascript) problems in a .Net Content-Managed Website

I have been trying to figure out how to set get a session cookie from Flash via Javascript. Yes, Flash does have a limited ability to set its own 'cookies' with something called **LocalStorage**, but there are a few advantages to actually creating 'real' cookies and working with those - not least because people understand browser cookies a little more than LocalStorage areas. The solution itself is pretty simple - you create a Javascript function to manipulate the cookie data, and then Flash uses the **ExternalInteface.call** function to access these javascript functions. If you want to go even more advanced, you can leverage getURL to create your Javascript functions in the first place - my favorate because it doesn’t need any external javascript. ( Sometime I'll clean out the code and post an example, but for now we're going to concentrate more on the problems encountered when using this solution. ) As I said, the solution is great and works in most situations however, this doesn’t work in the CMS we're using and I couldn’t figure out why. It turns that our problem was; 

## DOM Access

.Net pages put all the html inside a form and apparently this means that objects like embedded swfs become hidden from the Document Object Model in Internet Explorer. The solution to this is to “elevate” the object to be part of the window rather that the document. It seems that by creating a reference and using a different element in the heirarchy fixes DOM visibility issues. i.e. 

> window.objectID = document.getElementById(objectID);

A strange solution, huh? Ben Waldron has more information on this solution [here](http://blogs.popart.com/ben-waldron/archive/2007/11/08/flash-externalinterface-in-asp-net-applications.aspx).

## Comments

**[design](#342 "2008-06-08 14:12:48"):** Good points, but make it more generally

**[Aran Rhee](#343 "2008-06-09 02:08:39"):** James. I'd recommend using ExternalInterface for ALL flash browser communication to write the cookie etc rather than a direct attempt at getURL(javasctipt: .....) as the latest version of the Flash player disables most of this direct javascript calling functionality and I'm sure it will get locked down even further in the ever more stringent security sandboxing... In regards to Flash in a form issue, here is Adobe's official take on it (not that great really, but anyhow): http://kb.adobe.com/selfservice/viewContent.do?externalId=kb400730 Weird that a nested form tag fixes it.... There is also SWFFormFix here: http://www.teratechnologies.net/stevekamerman/index.php?m=01&y=07&entry=entry070101-033933

**[klick hier](#344 "2012-04-05 21:16:58"):** I think that is one of many most significant information personally. And i'm glad reading your article. But wanna remark on few general things, The site style is ideal, the articles is very excellent : D. Good job, cheers

