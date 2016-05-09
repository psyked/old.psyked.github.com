---
layout: post
title: XSLT and RSS feeds.
link: http://www.psyked.co.uk/xslt-and-rss-feeds/
author: psyked_james
description: 
post_id: 178
created: 2008/01/31 00:09:58
created_gmt: 2008/01/30 23:09:58
comment_status: open
post_name: xslt-and-rss-feeds
status: publish
post_type: post
---

# XSLT and RSS feeds.

XSLT is XSL Transformations, and XSL is Xtensible Stylesheet Language. (So says [w3schools](http://www.w3schools.com/xsl/default.asp)) XSLT is pretty impressive. With a single stylesheet you can completely reformat XML data into a HTML structure that suits your needs. Even better than that, you can also use quite complex commands to single out specific peices of data. This gets me thinking - RSS feeds are XML based - and RSS feeds are often formatted in the ugly default method of the browser. So why don't people use XSLT to completely refactor their RSS feed data, not least to maintain a bit of branding consistancy. Fast-forward a couple of hours development, and we have a beautiful XSL file that reformats our RSS XML into a layout not dissimilar to the main HTML pages. Now, fast forward again - and we're trying to make our RSS feeds look pretty in the browser. For some reason, the browsers' aren't utilizing our XSL stylesheet - both Firefox and IE are stubbornly refusing to use the XSL formatting when they encounter an RSS feed. XML is fine, but they're stubborn when it comes to the RSS varient. So, I guess the moral of the story might well be _**"if no-ones' using it, it's probably not possible? "**_ Irregardless, it was an interesting mini-project. If you're interested, you might want to have a look at these links; 

  * <http://www.w3schools.com/xsl/default.asp>
  * <http://www.w3.org/TR/xslt>

## Comments

**[jldugger](#273 "2009-06-01 22:27:48"):** They do, but they use more sophisticated tools like yahoo Pipes. [I wrote a small article](http://jldugger.livejournal.com/9134.html) a while back about this, and after reading up on XSLT I think it can probably be done with XSLT and (maybe, I need to read up on it) XProc.

