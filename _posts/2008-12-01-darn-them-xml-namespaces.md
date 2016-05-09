---
layout: post
title: Darn them XML namespaces!
link: http://www.psyked.co.uk/darn-them-xml-namespaces/
author: psyked_james
description: 
post_id: 399
created: 2008/12/01 09:30:17
created_gmt: 2008/12/01 08:30:17
comment_status: open
post_name: darn-them-xml-namespaces
status: publish
post_type: post
---

# Darn them XML namespaces!

Ugh, this E4X stuff is all a bit new to me - I'm still not used to namespaces and stuff.  For some reason I've had trouble extracting data from XML when I'm using a namespace.  I have no idea why, but it seemed that with the namespace in use, my attempts at extracting data from the XML returned blank data. Never fear!  It seems that either removing the namespace or replacing it with a wildcard would let me access the data.  Kudos to the blog posts of Riley (Got RIA?) : [Remove Annoying XML Namespaces in Flex / AS3](http://brianmriley.wordpress.com/2008/03/14/remove-xml-namespaces-in-flex-or-as3/) and [Getting around unknown namespaces in Flex / AS3](http://brianmriley.wordpress.com/2008/03/20/getting-around-unknown-namespaces-in-flex-and-as/). So until I get my head around how namespaces work, I'm going to be using the techniques described in the links above.  Until then, if anyone can explain this to me - I'd be very greatful!

## Comments

**[Jordi Boggiano](#478 "2008-12-01 11:58:13"):** Just had the same problem and a colleague gave me the solution, when you know what namespace to expect at least. class Foo { namespace blah = "http://url_of_your_xmlns_declaration"; use namespace blah; } If you set up your class like this, with the url used for the namespace in the xml file, and that use statement using it, you can then access everything properly. That being said, you should be careful because once you've namespaces, code like someXml.name() returns "http://namespaceUrl::realName", someXml.localName() returns only "realName" though.

**[Richard Butler](#479 "2008-12-01 14:10:50"):** A handy one if your XML only has one namespace is the following: default xml namespace = "http://my.xml.com/ns/1.0"; var x : XML = Test ; trace( x.node.item.text() ); // traces "Test"

**[Richard Butler](#480 "2008-12-01 14:13:04"):** Doesn't look like your comment system likes XML, but hopefully you can see what I was getting at!

**[James](#481 "2008-12-01 15:01:45"):** Aha, Akismet was eating the comments... Namespaces is something I'll have to look into a bit more. I'll give both of those suggestions a shot though, and see what I can make work... I was trying to extract the paths of the icons from the applicationDescriptor files in an AIR application (for my [ApplicationInfo](http://www.psyked.co.uk/actionscript/application-information-class-for-air.htm) class) but was getting stumped.

**[Nick Schneble](#482 "2008-12-01 17:55:33"):** James, You can easily handle multiple namespaces in XML using E4X without changing the namespace used in the class (per Jordi's comment). I wrote up a post on it a while back: http://userflex.wordpress.com/2008/04/03/xml-ns-e4x/ This technique can also be applied when you don't know what namespaces are specified beforehand, since you can iterate over the XML.namespaceDeclarations() array to determine what ones are used in the XML. Hope that helps!

**[James](#483 "2008-12-01 18:02:15"):** Thanks Nick - your post makes a lot of sense, my favourate solution so far!

**[Conu Adela](#484 "2011-06-02 10:04:09"):** If you are struggling with xml namespaces, there is a great tutorial on xpath namespaces at xml reports. It will be helpful and easy to look into. Here is the link: http://www.xml-reports.com/2011/05/xml-namespaces-for-dummies-part-1.html

