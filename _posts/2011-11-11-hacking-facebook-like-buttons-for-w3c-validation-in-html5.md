---
layout: post
title: Hacking Facebook "Like" buttons for W3C Validation in HTML5
link: http://www.psyked.co.uk/hacking-facebook-like-buttons-for-w3c-validation-in-html5/
author: psyked_james
description: 
post_id: 1433
created: 2011/11/11 01:11:03
created_gmt: 2011/11/11 00:11:03
comment_status: open
post_name: hacking-facebook-like-buttons-for-w3c-validation-in-html5
status: publish
post_type: post
---

# Hacking Facebook "Like" buttons for W3C Validation in HTML5

![](/wp-content/uploads/2011/11/html5-facebook.png) So, it turns out that the good old Facebook 'Like' buttons and Google's 'Plus one' buttons don't behave well on HTML5 format websites. That's because they make use of XHTML and namespaces. Sure, mixing XHTML and HTML5 together on a single page works just fine for the end-user, but when it comes to validating your pages on the W3C, it just won't work. What's the 'solution'? Why, hacking it, of course. Take the code for those elements out of the source, and embed it with JavaScript instead.  And it doesn't have to be complex either - you can use inline JavaScript code. Wrap your button embed HTML in a <script> tag, add a CDATA block, and encompass it in a `document.write()` function, and you're done. So this code:  Becomes this code:  Of course, this being a hack, I can't really speak for this being good practice, but it works. Evaluating the pitfalls will come later, I'm sure!

## Comments

**[James](#891 "2011-11-13 18:48:30"):** Interesting to note that there seems to be a new 'HTML5' option on the [Facebook Widgets](https://developers.facebook.com/docs/reference/plugins/like-box/) page, so perhaps I'm just a little behind the times!

**[Sam](#892 "2012-01-30 23:16:39"):** thank you, is there any other way except using iframe?

**[Rrugët](#893 "2012-04-09 17:30:28"):** http://www.facebook.com/plugins/like.php?href=http%3A%2F%2Fwww.psyked.co.uk%2Fflash%2Ffotb2011-highlight-1.htm&layout=standard&show_faces=false&width=450&action=recommend&colorscheme=light" scrolling="no" frameborder="0" allowTransparency="true" style="border:none; overflow:hidden; width:450px; height: 30px; align: left; margin: 2px 0px 2px 0px">

