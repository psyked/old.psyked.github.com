---
layout: post
title: XHTML, Hyperlinks and separating content from style.
link: http://www.psyked.co.uk/xhtml-hyperlinks-and-separating-content-from-style/
author: psyked_james
description: 
post_id: 130
created: 2007/10/15 21:58:51
created_gmt: 2007/10/15 20:58:51
comment_status: open
post_name: xhtml-hyperlinks-and-separating-content-from-style
status: publish
post_type: post
---

# XHTML, Hyperlinks and separating content from style.

XHTML is the attempt to purify the traditional mishmash of HTML standards, separating content from appearance, and to create a more elegant solution, for a more civilized age. That's great in theory - but unless you're armed with a plethora of cross-browser scripts and an iron will, moving to XHTML 1.0 Strict is a hard, bumpy road. And often one with little discernable gain. Did you know you can't use target attributes in link tags? Or alignment tags? Ok, so the alignment tags is a non-issue - we can do the same with CSS styles. But how, pray tell, do we achieve the feats we take for granted in HTML - target="_blank" ?  I've been pointed down the JavaScript road by several people, but I don't quite get how JavaScript is _the _solution after all, JavaScript made popup blockers what they are today. Nevertheless, here's [an interesting article from A List Apart](http://www.alistapart.com/articles/popuplinks). They cover several solutions, most of which are ugly and, well, not a real solution to avoiding the target attribute. The final option they cover however, is just the charm. 

![](http://uploads.psyked.co.uk/2007/10/alistapartcom.jpg)

### So, how does it work?

Well, the solution - if you can call it that - is a little more high-brow than the scripts I write from day-to-day, using listeners to hook into the click events of links, kidnap the urlrequest, and process it with JavaScript. The upside - you can leverage JavaScript onto any link, and perform far more complex tasks than the browsers' built-in links. The downside? It's a lot of preparation.