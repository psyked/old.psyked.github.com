---
layout: post
title: Executing multiple XMLHTTPRequests - successfully.
link: http://www.psyked.co.uk/executing-multiple-xmlhttprequests-successfully/
author: psyked_james
description: 
post_id: 369
created: 2008/12/03 13:15:30
created_gmt: 2008/12/03 12:15:30
comment_status: open
post_name: executing-multiple-xmlhttprequests-successfully
status: publish
post_type: post
---

# Executing multiple XMLHTTPRequests - successfully.

So I'm hacking together a simple client-side AJAX - based on [AHAH](http://en.wikipedia.org/wiki/AHAH) - and all of the example scripts only work with a single request.  Attempting to use the same script twice meant that the results would overwrite each other.  Ughh. The problem it turned out, was as a simple as the latter requests replacing the newer request, because their references were being overwritten.  So instead of using a single variable, I figured "why not pass the references around in the functions".  Here it is then, an AHAH-based set of AJAX functions, that works for multiple simultaneous function calls. Source code doesn't really work very well in my blog template, so I've put the functions in an external javascript file... [Click here to download the javascript file.](http://uploads.psyked.co.uk/2008/12/loadexternalcontent.js)

## Comments

**[PeteCook](#469 "2010-07-07 22:36:25"):** This is ace :)

**[Mikael](#470 "2011-03-01 15:38:28"):** If the laws of nature allowed it, I'd bear your children. Thanks :-)

**[Ercan MUTLU](#471 "2011-10-25 16:13:21"):** Hey MAN you THINK VERY GENIUSLY,AND ITS WORK PERFECT. I use your opinıon on my project AND works perfect.. THANK !.... There is solution STORRING HXL OBJ.TO ARRAY BUT IT LAKS MEMORY.... This solution avere seen is the BEST SOLUTION. HELLO FROM LOVELY COUNTRY TURKEY.

**[Omokoii](#472 "2012-01-17 16:36:59"):** Sweet bananas, this is what I was looking for ^^

**[Laurent](#473 "2012-06-16 14:39:19"):** This is ACE!!!! Cheers!

**[Daniel Campos](#474 "2013-03-08 15:06:09"):** Thanks, elegant solution to the problem of concurrent ajax requests (worked well here)

**[Renald Camilleri](#475 "2013-05-10 17:35:10"):** Really a neat solution, thank you :)

