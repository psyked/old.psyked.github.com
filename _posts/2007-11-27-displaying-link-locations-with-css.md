---
layout: post
title: Displaying Link locations with CSS
link: http://www.psyked.co.uk/displaying-link-locations-with-css/
author: psyked_james
description: 
post_id: 161
created: 2007/11/27 09:01:15
created_gmt: 2007/11/27 08:01:15
comment_status: open
post_name: displaying-link-locations-with-css
status: publish
post_type: post
---

# Displaying Link locations with CSS

### Why would you want too?

How often is it the case that you're not _quite_ sure where a link is going to take you? Ok, so it's not a major issue for mainstream browsers - after all, that's what the "Status bar" is for. But beyond your normal browser operation - say on an unusual machine or if you're looking at a print-off - just how can you tell where a link should be going? If the link text is good, you might be able to track down the target page, but that's nothing compared to the usefullness of a full URL. Luckily with a smidgen of CSS and an up-to-date browser, you can solve at least a few of these problems in a nice, clever way. A List Apart covered this in the misty old era of 2002, back when I was still making HTML pages with notepad and cobbling together images with Trial versions of Paint Shop Pro. In the article, [CSS Design: Going to Print](http://www.alistapart.com/articles/goingtoprint/), they Eric Meyer covers - amongst other things - the issue of displaying 'Printed links', making links that are as useful in print as they are functional onscreen.

### What do I have to do?

The long and short of it is this snippet of code; `#content a:link:after, #content a:visited:after { content: " (" attr(href) ") "; font-size: 90%; }`

### How does it work?

Well, the ':after' selectors are pseudo-selectors under the CSS 2.1 spec, and can add styles to an imaginary object that is created after the chosen item. In this case, it's doubled up with the 'content:' property, one that can generate basic text. This is really the usage that the ':before', ':after' and 'content:' properties / selectors were invented for. Following the 'content:' property is a bit of calculation - about as complex as CSS calculations can get - and is effectively adding two strings and a property together to generate the content. The 'attr(href) ' is dynamically pulls in the href attribute of the selected HTML object. It could pretty much be used on any attribute, though. What's the final result? That's simple. Any links in the #content element of the page will automatically have their href / url displayed as text after the link itself. That way you can easily see where they go, without relying on things like the status bar. Especially useful if you're creating printable version of pages, because of how seemlessly it will display. It seems curious that I haven't seen this in action much - presumably because the article was so old before the major browsers caught up with the CSS 2 specs. Who knows? 

### In action...

Nick La, over at [Web Designer Wall](http://www.webdesignerwall.com/), uses a very similar technique for the comments section of his website. When you roll over the commenters' name, it displays - in plain text - the url associated with that commenter. This is however, done without this method, in favor of what I assume to be a nice cunning bit of ':hover' pseudoclasses and 'display:' properties. It just goes to show that this idea doesn't have to be limited to print stylesheets. There is now an example using this technique to display email address locations at <http://css-tricks.com/better-email-links-featuring-css-attribute-selectors/>. Check it out!

## Comments

**[css](#262 "2008-11-11 22:50:36"):** Cascading Style Sheets (CSS) web design lessons Css link Properties Attributes - examles http://css-lessons.ucoz.com/link-css-examples-1.htm http://css-lessons.ucoz.com/link-css-examples-2.htm

**[mayra veronica mamma mia](#263 "2013-09-14 17:27:28"):** It's a pity you don't have a donate button! I'd certainly donate to this fantastic blog! I guess for now i'll settle for bookmarking and adding your RSS feed to my Google account. I look forward to new updates and will share this website with my Facebook group. Talk soon!

**[mayra veronica video](#264 "2013-09-25 07:19:26"):** This is very interesting, You are a very skilled blogger. I've joined your rss feed and look forward to seeking more of your great post. Also, I've shared your website in my social networks!

