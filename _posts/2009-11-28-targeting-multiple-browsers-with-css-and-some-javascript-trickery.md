---
layout: post
title: Targeting multiple browsers with CSS... and some Javascript trickery.
link: http://www.psyked.co.uk/targeting-multiple-browsers-with-css-and-some-javascript-trickery/
author: psyked_james
description: 
post_id: 1045
created: 2009/11/28 09:00:19
created_gmt: 2009/11/28 08:00:19
comment_status: open
post_name: targeting-multiple-browsers-with-css-and-some-javascript-trickery
status: publish
post_type: post
---

# Targeting multiple browsers with CSS... and some Javascript trickery.

There's a clever little javascript library that allows you to write CSS specifically for Chrome, the iPhone, IE 8, etc. all in a single file.  What it does is manipulate the HTML document client-side to add additional classes to the page, based on your browser type.  The end result is that your page gets additional selectors like .ie or .gecko added - and you can setup a single CSS file to target all of these browsers in one shot - no server side magic or conditional comments in the HTML. You can find more information here ( <http://snipplr.com/view/9340/css-browser-selector/> ) or download it from here (<http://github.com/rafaelp/css_browser_selector> ).

## Comments

**[Josh](#712 "2009-11-29 05:30:28"):** This is interesting. A good idea, but if IE followed the standards we wouldn't have to worry about crazy fixes like this. I know that IE isn't the only problem for many people. There are designers out there that want their designs to look identical across browsers (I was one of them in the beginning). You have to realize though, that the reality of the web is that different browsers will display things slightly differently. Our job as designers is to make them look as close as possible, but accept a certain amount of variation. Honestly, as long as the experience is the same and the designs look mostly alike, most visitors won't see the difference -- if not because of any other reason than most visitors only use one browser.

**[James](#713 "2009-12-02 09:56:57"):** I wish more designers were pragmatic enough to accept that different browsers behave differently! Getting things consistent can easily take as long as the initial development - even with this javascript trick, you're still developing two or three different stylesheets.

